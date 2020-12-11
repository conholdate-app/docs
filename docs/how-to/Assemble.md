---
id: assemble-forms-online-free
title: Assemble Forms Online
sidebar_label: Assemble Forms
---

Assemble your own forms and document wizards online made easy with our document assembly engine.

## What is Forms
Forms is a web-based app used to generate documents using a pre-defined templates in a wizard a-like step-by-step form.
Imagine that you have two similar documents with few minor differences, with Forms you can keep only one document as template and generate desired output anytime you want.
The result from filling up the form can be obtained as PDF, DOC and DOCX (more formats coming soon) or emailed to preset email addresses.

## How to create Forms
In order to create your own Form it is required to create two files: **docx** and **xml** with equal names.
For example: `my_form.docx` and `my_form.xml`
> Download our [form](/download?template=example-forms.zip) example for the further reference.

### DOCX template
DOCX template is your main template which holds static data/text along with dynamic data/variables.
1. Open existing or create new DOCX file;
1. Now type any `TAG` (a.k.a. `ID`) where you want to submit dynamic data.
	> `TAG` must be unique in order to work correctly  
	> TAG Example: `<<[myTag]>>`

### XML template
XML template structure is simple and devided by `sections` inside root element `form`. Each `section` represents form/wizard step.
1. Create new XML file;
1. Add root element `<form></form>`;
1. Inside `<form>` add `<section></section>`;
1. Now we can add `<question></question>`. Each `section` can have as many `questions` as you want.
1. Each `<question>` must have:
	- type
	- id
	- title
	- description
	Where `id` = `tag` name from DOCX file.

See following XML example:
```xml
<form>
	<section>
		<question>
			<type>input</type>
			<id>myTag</id>
			<title>My title</title>
			<description>Input description, question, etc</description>
		</question>
		<question>
			<type>textarea</type>
			<id>myAnotherTag</id>
			<title>Another title</title>
			<description>textarea description, question, etc</description>
		</question>
	</section>
	<section>
		<question>
			<type>dropdown</type>
			<id>myDropdownTag</id>
			<title>One more title</title>
			<description>dropdown description, question, etc</description>
			<required>true</required>
			<options>
                <option>Option 1</option>
                <option>Option 2</option>            
            </options>
		</question>
	</section>
</form>
```
This example has 2 steps, where first step has 2 questions with text input and text area and second step has one question with dropdown menu.

### Supported question types
- input
- textarea
- dropdown
- checkbox
- radio button
- date picker

### Advanced settings
With advanced option you can specify required or optional questions, allow/disalow downloads and sent resulted documents to provided email addresses.
- To set any question as required just add `<required>true</required>` parameter to `<question></question>` property. Setting to **false** means that question is optional.
	By default it is set as **ture** - required.
- Allowing/disalowing downloads and sending resulted documents can be achieved by added `<settings>` property inside root element `<form>`, in the same way as you did for `<section>`.
	Example:
	```xml
		<form>
		...
			<settings>
				<download>
					<enable>true</enable>
					<downloadAs>PDF, DOCX</downloadAs>
				</download>
				<email>
					<enable>true</enable>
					<emailTo>test@email.com, test@secondemail.com</emailTo>
					<emailAs>DOCX</emailAs>
				</email>
			</settings>
		...
		</form>
	```

### Assemble template
Now that you have both DOCX and XML templates it is time to asseble your form.
In order to asseble your final template, just zip both files into single zip.
	
### Create forms online without registration
1. Go to [Online Document Assembly](https://features.conholdate.app/assembly) page.
1. Click on `Upload` icon and upload a zip package.
1. After upload is complete, click on `Assembly` button.
1. To share your form click on <i class="far fa-copy"></i> button. Share form link will be copied to your clipboard.
1. If download resulted document is enabled you can select one of the three available formats from dropdown and download it.

### Create forms online as registered user
Registered users can assemble template(s) right from dashboard.
1. [Login](https://conholdate.app/signin) to your account or [register](https://conholdate.app/signin) if you do not own one yet. It's FREE!
1. Go to your [dashboard](https://dashboard.conholdate.app).
1. Go to `My Forms` section.
1. Click on `Upload` button and upload a zip package.
1. Wait until uploading and processing is complete, then click on <i class="fas fa-ellipsis-v"></i> icon and select `Assembly`.
1. Complete form by going through all steps.
1. Click on **Finish** button to generate document with parameters you inserted during wizard steps.
1. If download resulted document is enabled you can select one of the three available formats from dropdown and download it.

## Responsive design
View your documents on any mobile or desktop devices from anywhere! [Conholdate.app](https://conholdte.app) provides a responsive layout.

## Cross-browser support
All major browsers such as Safari, Chrome, Firefox, Opera and Edge are supported out of the box.

## Supported formats
Currently our free online document assembly supports only **DOC** and **DOCX** templates. But we work on new formats adding.