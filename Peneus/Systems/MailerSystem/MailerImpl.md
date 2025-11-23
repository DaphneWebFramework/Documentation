# MailerImpl

Sends SMTP emails using PHPMailer (>= 6.10.0).

## Methods

### __construct

Constructs a new instance by initializing PHPMailer with the provided
configuration values.

#### Syntax

```php
public function __construct(\Peneus\Systems\MailerSystem\MailerConfig $mailerConfig, ?\PHPMailer\PHPMailer\PHPMailer $phpMailer = \Peneus\Systems\MailerSystem\null)
```

#### Parameters

- **$mailerConfig**: The configuration values used to initialize the PHPMailer instance.
- **$phpMailer**: (Optional) The PHPMailer instance to use. If not specified, a default instance is created.

---

### SetAddress

Sets the recipient email address.

#### Syntax

```php
public function SetAddress(string $email): static
```

#### Parameters

- **$email**: The destination email address.

#### Return Value

The current instance.

---

### SetSubject

Sets the subject line of the email.

#### Syntax

```php
public function SetSubject(string $subject): static
```

#### Parameters

- **$subject**: The subject text of the message.

#### Return Value

The current instance.

---

### SetBody

Sets the body of the email.

#### Syntax

```php
public function SetBody(string $body): static
```

#### Parameters

- **$body**: The full HTML or plain text content of the email.

#### Return Value

The current instance.

---

### Send

Sends the email message.

#### Syntax

```php
public function Send(): bool
```

#### Return Value

Returns `true` if the message was sent successfully, `false` otherwise.

---

### LoggerCallback

Internal PHPMailer debug output handler.

#### Syntax

```php
public function LoggerCallback(string $str, int $level): void
```

#### Parameters

- **$str**: The debug message.
- **$level**: The debug level.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
