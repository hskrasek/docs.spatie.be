---
title: Making your attachments interactive
---

On top of adding attachments to your messages, you can also make your attachments interactive. 

Take a look at this response on Slack:

<img src="/images/slack/buttons.png">

This is how you would build that up

```php
$this->respondToSlack()
    ->withAttachment(Attachment::create()
        ->setColor('good')
        ->setText('This is good!')
        ->setCallback('good-message')
        ->addAction(Action::create('cool button', 'A Cool Button', 'button'))
    );
```

Take a look at [Slacks documentation on interactive messages](https://api.slack.com/interactive-messages) to learn what's possible. Please note that at this time only buttons are supported, and menus are not.
