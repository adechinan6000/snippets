## Send mail

* dependencies

```bash
compile group: 'javax.mail', name: 'mail', version: '1.4.7'
compile group: 'javax.mail', name: 'javax.mail-api', version: '1.5.1'
```

* usage

```bash
// Step1
System.out.println("setup Mail Server Properties..");
Properties properties = new Properties();
properties.put("mail.smtp.host", "587");
properties.put("mail.smtp.auth", "true");
properties.put("mail.smtp.starttls.enable", "true");
Session session = Session.getDefaultInstance(properties, null);

// Step2
System.out.println("setting receiver and content mail..");
Message message = new MimeMessage(session);
message.setRecipient(Message.RecipientType.TO, new InternetAddress("worktestworktest@yahoo.com"));
message.setRecipient(Message.RecipientType.CC, new InternetAddress("test2@crunchify.com"));
message.setSubject("Message from admin..");
String emailBody = "Happy to hire you. " + "<br><br> Regards, <br>Salami";
message.setContent(emailBody, "text/html");

// Step3
System.out.println("sending..");
Transport transport = session.getTransport("smtp");
transport.connect("smtp.gmail.com", "atsk1618@gmail.com", "1984sunsetboulevard");
transport.sendMessage(message, message.getAllRecipients());
transport.close();
```

* attach file

```bash
// Create Mime Content
MimeBodyPart messageBodyPart = new MimeBodyPart();
String html = "<H1>Important Message</H1>";
messageBodyPart.setContent(html, "text/html; charset=utf-8");
MimeBodyPart fileBodyPart = new MimeBodyPart();
fileBodyPart.attachFile("/path-to/attach.txt");
MimeBodyPart fileBodyPart2 = new MimeBodyPart();
fileBodyPart2.attachFile("/path-to/attach2.txt");
Multipart multipart = new MimeMultipart();
multipart.addBodyPart(messageBodyPart);
multipart.addBodyPart(fileBodyPart);
//add another body part to supply another attachment
multipart.addBodyPart(fileBodyPart2);
message.setContent(multipart);
```