# Demo AWS SES SMTP

Demonstration of:

* Amazon Web Services (AWS)

* Simple Email Service (SES)

* Simple Mail Transfer Protocol (SMTP)

* Using the command line to send email

Contents:

* [](#)


## Documentation

[Amazon Simple Email Service - Developer Guide](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/ses-dg.pdf)

[Amazon SES SMTP Issues](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/troubleshoot-smtp.html)

[Testing Email Sending Using the Command Line](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/send-email-smtp-client-command-line.html)


## Security and TLS

For security, we prefer port 465 with implicit TLS encryption, rather than port 587 with STARTTLS.

https://www.fastmail.com/help/technical/ssltlsstarttls.html



## Connect

Connect via the command line:

```sh
openssl s_client -crlf -quiet -connect email-smtp.us-east-1.amazonaws.com:465 < message.txt
```

Response:

```sh
depth=4 C = US, O = "Starfield Technologies, Inc.", OU = Starfield Class 2 Certification Authority
verify return:1
depth=3 C = US, ST = Arizona, L = Scottsdale, O = "Starfield Technologies, Inc.", CN = Starfield Services Root Certificate Authority - G2
verify return:1
depth=2 C = US, O = Amazon, CN = Amazon Root CA 1
verify return:1
depth=1 C = US, O = Amazon, OU = Server CA 1B, CN = Amazon
verify return:1
depth=0 CN = email-smtp.us-east-1.amazonaws.com
verify return:1
220 email-smtp.amazonaws.com ESMTP SimpleEmailService-d-N8DNVJOVF 1hh7w7XwCXyEHPypK4v6
250-email-smtp.amazonaws.com
250-8BITMIME
250-SIZE 10485760
250-AUTH PLAIN LOGIN
250 Ok
334 VXNlcm5hbWU6
334 UGFzc3dvcmQ6
235 Authentication successful.
250 Ok
250 Ok
354 End data with <CR><LF>.<CR><LF>
250 Ok 01000170d10e6a6c-71c65177-ce88-4135-9258-48c0e8bf916d-000000
```
