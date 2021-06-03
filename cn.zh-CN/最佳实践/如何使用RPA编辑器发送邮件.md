如何使用RPA编辑器发送邮件 
===================================

本文主要介绍基于Python语法，使用RPA编辑器编写发送邮件的流程，将文本信息或者附件按设定好的发件箱和收件箱进行邮件传输。

场景简介 
-------------------------

使用RPA获取到数据、下载好对应文件后，有可能遇到需要发送邮件的场景，需要通过邮件的形式发送固定格式的正文及附件内容，此时可以继续在RPA中编写发送邮件相关操作的流程，使得整个自动化流程完整连贯地执行。

关键代码 
-------------------------

发送邮件仅需使用Python内置库，不涉及第三方包，登录进入RPA编辑器主界面，参考以下代码，按需更改参数即可。

    from rpa.core import *
    from rpa.utils import *
    import rpa4 as rpa # 使用V4引擎
    import smtplib
    from email.mime.text import MIMEText
    from email.mime.image import MIMEImage
    from email.mime.multipart import MIMEMultipart
    from email.header import Header
    from email.mime.application import MIMEApplication
    import random
    
    # 使用SMTP服务需要获取SMTP授权码，
    
    def test():
        sender = "发件人邮箱@xx.com"
        receiver1 = "收件人邮箱1@xx.com"
        receiver2 = "收件人邮箱2@xx.com"
        # 构造邮件类，输入关键的发件人和收件人信息
        test = Mail("smtp.qq.com",sender,[receiver1,receiver2])
    
        # 为邮件实例设定"SMTP"授权码，对应授权码可以在邮箱提供方对应设置页面获取
        test.password = "xxxx"
    
        # 创建邮件正文文本，邮件正文使用Html进行编辑，方便插入表格及字体样式
        text = test.create_html_table([["标题1","标题2","标题3"],[1,2,3]])
        text = "<h1>邮件发送测试</h1><p>此邮件发送自python</p>"+text 
    
        # 指定邮件标题
        title = "测试邮件发送功能"
    
        # 指定附件绝对路径
        file_path1 = r"D:\综合归档\03.测试代码\测试用例\CMS信息录入测试.xlsx"
        file_path2 = r"D:\综合归档\03.测试代码\测试用例\CMS信息录入测试.xlsx"
        file_paths = {"附件1.xlsx":file_path1,"附件2.xlsx":file_path2}
        
        # 将邮件标题、正文、附件路径写入到邮件类中
        msg =  test.write_mail(title,text,file_paths)
        
        # 发送邮件
        test.send_mail(msg)
    
    
            
    # 邮件处理类
    class Mail(object):
        """
        邮件类工具，主要用于处理发邮件等操作，支持向正文中插入表格、文本、图片等形式
        1.构造方法中，需要输入smtp服务器名，发件人地址，收件人地址列表
        2.生成实例后，需要给实例的password赋值（即发件人smtp密码）
        3.write_mail方法需要传入参数收件人别名（多个收件人会用同一个名字）,邮件主题,html文本,附件路径(字典，附件名：附件绝对路径)
        4.send_mail方法需要传入参数msg，即write_mail方法的返回值。
        5.提供create_html_table工具方法，传入二维列表，自动生成html表格，可以作为html文本写到邮件正文中
        """
        # 初始化内容，smtp服务器，发件人地址，发件人smtp密码（初始为空），收件人地址列表
        def __init__(self, smtp_server:str, sender:str, receivers:list)->None:
            self.smtp_server = smtp_server
            self.sender = sender
            self.password = ""
            self.receivers = receivers
            pass
    
        
        # 根据二维列表生成对应的HTML表格
        def create_html_table(self,data):
            """
            根据二维列表生成对应的html文本\t
            Args:\t
                data(list<list>):二维列表\t
            Returns:\t
                html_table(str):html字符串\t
            """   
            html_table = "<table border=1>"
            for row in data:
                tr = "<tr>"
                for col in row:
                    td = "<td>"+str(col)+"</td>"
                    tr += td
                tr += "</tr>"
                html_table += tr
            html_table += "</table>"
            return html_table
    
        # 填写邮件内容
        def write_mail(self,receivers_alias,title,html_text,file_paths):
            """
            编写邮件内容，传入文件名\t
            Args:\t
                receivers_alias(str):收件人称谓\t
                title(str):邮件主题\t
                html_text(str):HTML文本，可以以此生成表格、链接、图片等信息\t
                file_paths(dict<str:str>):需要发送的附件的完整路径字典，形如文件名（需带后缀）:文件绝对路径\t
            Returns:\t
                msg:email模块的MIMEMultipart对象，可以带附件，带HTML文本\t
            """
            msg = MIMEMultipart()
            # 头信息
            msg['From'] = Header(self.sender)
            # 这里的收件人是指头信息中的收件人称呼，多个收件邮箱的情况下，收件方只能看到统一的称呼，看不到发送给了其他的谁
            msg['To'] = Header(receivers_alias)
            msg['Subject'] = Header(title)
        
            html_message = MIMEText(html_text, 'html', 'utf-8')
            msg.attach(html_message)
        
            # 添加多个附件
            if len(file_paths)>0:
                for key,value in file_paths.items():
                    with open(value,'rb') as attach_file:
                        file_content = attach_file.read()
                    file_part = MIMEApplication(file_content)
                    file_part.add_header('Content-Disposition', 'attachment', filename=key)
                    msg.attach(file_part)
            
            return msg
    
        # 发送邮件
        def send_mail(self,msg):
            """
            将给定的msg作为邮件内容向指定的收件人地址列表发送\t
            Args:\t
                msg(MIMEMultipart):邮件正文对象\t
            Returns:pass\t
            """
            try:
                # 开启发信服务，这里使用的是加密传输
                server = smtplib.SMTP_SSL(self.smtp_server)
                server.connect(self.smtp_server,465)
                # 登录发信邮箱
                server.login(self.sender, self.password)
                # 发送邮件
                server.sendmail(self.sender, self.receivers, msg.as_string())
                # 关闭服务器
                server.quit()
                print('success')
            except smtplib.SMTPException as e:
                print('error',e)
            pass


