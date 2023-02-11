# Email Template Generator for TED Events

This is a utility repo to generate and store automated email templates for TED applicants, registrants, and attendees. It's built using [MJML](https://documentation.mjml.io/), which handles converting readable code into ugly HTML that seems to be client friendly. Importantly, it helps inline all of our CSS to ensure that formatting works across email clients, even after forwarding/replying.

Today, this is setup to work with [Mandrill](https://mandrillapp.com/templates), a Mailchimp app used for transactional email. The hope is that these templates are agnostic enough to be able to transition to a different provider in the future should they need to.

### Repo Organization

The repo is organized by event, so that the templates can be customized by event.

_Note: yes, you're right. It'd be super cool to make an event agnostic template that's super customizable and flexible, but doesn't require repeated work. You should totally do that._

Inside each event directory is a set of templates, each with a respective `.mjml` and `.html` file. Use the `.mjml` as an editable template, which the MJML package can than output to ugly HTML, ready to paste into Mandrill.

### Usage

There are a few options for development. The first and perhaps easiest is to preview in real time using the MJML VSCode Extension (I'm using mjmlio.vscode-mjml, take your pick because there's a few). This works great, however you can't inspect the resulting HTML, so if you run into a snag, debugging can be a little tricky.

Additionally, you can use the MJML command line tool to watch your `.mjml` file for changes, and render out into `.html` in real time using the following command:

`mjml -w [input.mjml] -o [output.html]`

Then feel free to open the output file in your browser of choice, though you will need to refresh to see changes.
