# SendHTMLEmailUiPath
Workflow to send HTML Emails with Images via SMTP. You can create your own HTML template with specific Styles and Workflow will process content to generate and send the MIME-Message.  

This workflow is based on Mailkit - Mimekit libraries (https://github.com/jstedfast/MailKit)


Refer to documentation at https://github.com/andresm9/SendRichEmailUiPath/blob/master/documentation/readme_es.md in Spanish 



## Getting Started

Make sure you have imported these namespaces before start:

- Mailkit
- Mimekit

![Namespaces](https://github.com/andresm9/SendRichEmailUiPath/blob/master/documentation/image-20200901011214809.png)

### HTML Content

HTML Content depends on what kind of email you are sending. Take into Account best practices and techniques to get a Better HTML Email compatible with your target email client.


## Arguments

| Argument                  | Description                                                  | Default                                                      |
| ------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| in_ContentEmailFolderPath | Path to folder where HTML is with images                     | "emailcontent"                                               |
| in_EmailHostname          | name of SMTP Server                                          | "localhost"                                                  |
| in_EmailPort              | Port of SMTP Server                                          | 25                                                           |
| in_EmailUseSSL            | (NOT USED) Boolean to choose if Connection to SMTP Server is secure (SSL/TLS) or not | By default, Connect Method sets as "Auto" Option.            |
| in_LoginUsername          | If needed, Username to login to SMTP Server                  | Leave in blanks if Server doesn't require Auth               |
| in_LoginPassword          | If needed, Password to login to SMTP Server                  | Leave in blanks if Server doesn't require Auth               |
| in_ListOfRecipients       | List of Type **System.Collections.Generic.List<MimeKit.MailboxAddress>** which contains All addresses from Recipients<br />**How to Use:**<br /><br />`new List(Of MailboxAddress) From { new MailboxAddress("Name Recipient 1","recipient1@example.com"),new MailboxAddress("Name Recipient 2", "recipient2@example.com"), new MailboxAddress("other_recipient@example.com")}` | By Default it's a empty List <br />`new List(Of MailboxAddress)` |
| in_ListOfSenders          | List of Type **System.Collections.Generic.List<MimeKit.MailboxAddress>** which contains the Sender (or senders if supported)<br /><br />**ALERT: Some SMTP servers doesn't support Multiple Senders. Use only one element in the list**<br /><br />**How to Use**<br /><br />`new List(Of MailboxAddress) From { new MailboxAddress("Name Sender","sender@example.com")}` | By Default it's a empty List <br />`new List(Of MailboxAddress)` |
| in_CCAddresses            | List of Type **System.Collections.Generic.List<MimeKit.MailboxAddress>** which contains All addresses from Recipients in the CC Section of the message<br />**How to Use:**<br /><br />`new List(Of MailboxAddress) From { new MailboxAddress("Name Recipient 1","recipient1@example.com"),new MailboxAddress("Name Recipient 2", "recipient2@example.com"), new MailboxAddress("other_recipient@example.com")}` | By Default it's a empty List <br />`new List(Of MailboxAddress)` |
| in_BCCAddresses           | List of Type **System.Collections.Generic.List<MimeKit.MailboxAddress>** which contains All addresses from Recipients in the BCC Section of the message<br />**How to Use:**<br /><br />`new List(Of MailboxAddress) From { new MailboxAddress("Name Recipient 1","recipient1@example.com"),new MailboxAddress("Name Recipient 2", "recipient2@example.com"), new MailboxAddress("other_recipient@example.com")}` | By Default it's a empty List <br />`new List(Of MailboxAddress)` |
| in_ReplyToAddresses       | List of Type **System.Collections.Generic.List<MimeKit.MailboxAddress>** which contains Address for "Reply-To" Section of the message<br />**ALERT: Some SMTP servers doesn't support Multiple Reply-To Addresses. Use only one element in the list**<br /><br />**How to Use**<br /><br />`new List(Of MailboxAddress) From { new MailboxAddress("Name ReplyTo","replyto@example.com")}` | Por defecto es una Lista Vacia <br />`new List(Of MailboxAddress)` |
| in_Subject                | Subject of the Email                                         | String.Empty                                                 |
