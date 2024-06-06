*LinkedIn / Email:*

At asioso / yukon we like to put new technology into action. This is why, together with our partner yukon / asioso we have built an AI text generator based on ChatGPT for the widely acclaimed open source PIM and CMS Pimcore. "Ghostwriter" comes as a Pimcore plug-in that seamlessly integrates AI into the Product Information and Content Management UIs of Pimcore. Prompts can be easily configured and tuned on a per-filed basis and may also dynamically reference text or data already available in the PIM data object, content module or page. Writing an SEO text or product description now is just a click: Ghostwriter will use the page's meta data or the product's technical information to create the required copy.

XXX Bild folgt

*Pimcore PlugIn page:*

![](documentation/img/001.png)

Ghostwriter: Configurable AI Text Generator for Data Objects and Bricks

**Marketing Tools**

**Project Summary**

"Ghostwriter" seamlessly integrates AI into Pimcore’s PIM and CMS UIs. Prompts can be easily configured and tuned on a per-filed basis for both data objects and bricks. Prompts can contain placeholders that dynamically reference text or data already available in the data object, brick or page. Writing e.g. an SEO text or product description now is just a click: Ghostwriter will use the page's meta data or the product's technical information to create the required copy.

**Readme**

**Features**

- Add AI text generation to text and rich text fields in data objects
- Add AI text generation to text and rich text fields in bricks
- Configure the prompts sent to ChatGPT on a per-field basis
- Add placeholders to your prompts that will pull actual data from the data object at hand, from the brick or the page (document) at hand and add the data to your prompt dynamically before it is being sent to ChatGPT
- Configure multiple shortcut commands in addition to the main prompt, e.g. for shortening, extending or translating the field’s content.
- Multi language support

**Prerequisites**

You will need a paid ChatGPT account to use the ChatGPT API. See <https://help.openai.com/en/articles/7039783-how-can-i-access-the-chatgpt-api> for details. Your individual API key will be assigned after you sign up with OpenAI. It needs to be added to the Ghostwriter configuration before you will be able to send requests to ChatGPT. Costs for OpenAI will depend on the volume of requests you send. As of writing this manual, there was a free request volume you can use for testing without being charged.

**Configuration**

Configuration is done in data objects. There is a **global configuration** object that takes the ChatGPT API key and a few other settings as follows:

![](documentation/img/002.png)

This is also where you add so called shortcuts. Shortcuts are prompts that will be shown with all fields you configure. You should use them to globally add prompts for things like shortening or extending text length, change tonality or translate text. A shortcut can not reference data from other fields, it uses the chat history as an input only.

In order to add the Ghostwriter features to your PIM and CMS UI, you will also have to **add field configuration** objects. This is where all the prompt engineering is done on a per field level.

![](documentation/img/003.png)

Find more documentation on how to use placeholders like e.g. {seo.title} directly in the configuration UI.


**How to get plugin**

You can write an email to [christoph.ramm@yukon.de](mailto:christoph.ramm@yukon.de).

***Installation***

Then you will get two options to install plugin.
First one is to get access token that you need to use if you want to install plugin from our Private Package Repository (Recommended way of installation). Following next commands:
```bash
composer config --global --auth http-basic.asioso-ghostwriter.repo.repman.io token YOUR-TOKEN
```
```bash
composer config repositories.asioso composer https://asioso.repo.repman.io/
``` 

Second option is to get package as zip file, upload the zip file to your project (create a folder `bundles` in the Pimcore root folder) and add the following to your `composer.json`:
```json
"repositories": [
{
"type": "artifact",
"url": "./bundles/"
}
]
```
Whatever approach you used, when you finish these steps you should be able to execute next commands.

```bash
composer require asioso/ghostwriter-bundle
``` 

```bash
php bin/console pimcore:bundle:enable GhostwriterBundle
``` 

```bash
php bin/console pimcore:bundle:install GhostwriterBundle
``` 

**Further reading**

The quality of the prompts you configure will have a huge impact on how useful Ghostwriter will be for your end users. You may even want to give end users access to the prompt configuration if they are savvy in prompt writing. This is OpenAI’s official prompt engineering guide: <https://platform.openai.com/docs/guides/prompt-engineering>

If you want to understand why the text lengths you configure in the field configuration is never 100% precise, please read about ChatGPT’s “token” concept here: <https://help.openai.com/en/articles/4936856-what-are-tokens-and-how-to-count-them>

**Authors and contact**

The Ghostwriter plugin is a joint development of:

**asioso GmbH**
Wilhelmine-Reichard-Str. 26
80935 München
Germany
[www.asioso.de](http://www.asioso.de)

**yukon consulting GmbH**
Waldpromenade 40b
82131 Gauting
Germany
[www.yukon.de](http://www.yukon.de)** 





