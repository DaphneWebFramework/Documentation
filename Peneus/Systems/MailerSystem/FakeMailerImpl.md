# FakeMailerImpl

Simulates email sending without dispatching any real messages.

Used during development or testing to mimic a successful email delivery
without connecting to an SMTP server or external mail service.

## Methods

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

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
