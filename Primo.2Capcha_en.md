# Primo.2Capcha Package Description

The **Primo.2Capcha** package is a set of tools for automatically solving CAPTCHA through the external 2Captcha service. It supports working with text CAPTCHAs (including text on images), as well as hCaptcha and ReCaptcha.

## General Information

**Primo.2Capcha** is a powerful tool that simplifies interaction with various types of CAPTCHAs by automating their resolution. It supports popular CAPTCHA formats like hCaptcha and ReCaptcha, making the package versatile for working with modern web forms.

## Getting Started

To install the **Primo.2Capcha** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Manage dependecies`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo RPA** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.2Capcha** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For more detailed information on setting up and using **Primo.2Capcha**, visit [the documentation on our website](https://docs.primo-rpa.com).

## Library Composition

The library includes the following features:

- Solve hCaptcha
- Solve ReCaptcha v2
- Solve ReCaptcha v3
- Solve question
- Solve image

To use an element, simply drag it into the workspace of your Primo RPA Studio project.

## Element Properties

### General Properties

The following properties are common across multiple elements and are defined under the **General** section:

- **Continue on exception**: The script will continue running even if an error occurs during the execution of the element.
- **Disable logging**: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to `File > Settings > General > Elements` and set the desired value in the `Disable logging for new elements` checkbox.
- **Name**: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical components are used.
- **Screenshot on error**: A screenshot will be taken if an error occurs.
- **Screenshot on finish**: Allows taking a screenshot upon the element's completion. All screenshots are saved in the `.Screenshots` folder, which is automatically created inside the process folder.
- **Wait after (ms)**: Pause after the element is executed.
- **Wait before (ms)**: Adds a pause before the element is executed.

### Solve hCaptcha

Element for solving hCaptcha:

1. **Output:**
   - Result — the result of the CAPTCHA resolution.
2. **Parameters:** (required):
   - URL
   - URL API
   - API Key
   - Site key
   - Time-out

To solve the CAPTCHA, locate the `data-sitekey` value in the source code of the page, insert it into the "Site key" field, then place the obtained token into the hidden `h-captcha-response` and `g-recaptcha-response` fields, and submit the form.

### Solve ReCaptcha v2

Element for solving ReCaptcha v2:

1. **Output:**
   - Result — the result of the CAPTCHA resolution.
2. **Parameters:** (required, except for the "Invisible" parameter):
   - URL
   - URL API
   - API Key
   - Site key
   - Invisible
   - Time-out

To solve the CAPTCHA:
1. Find the link starting with `www.google.com/recaptcha/api2/anchor`, or locate the `data-sitekey` parameter.
2. Copy the value of the `k` parameter from the link or the `data-sitekey` value.
3. Locate the element with id `g-recaptcha-response` and remove the `display:none` attribute to make it visible. Insert the token into this field and submit the form.

### Solve ReCaptcha v3

Element for solving ReCaptcha v3:

1. **Output:**
   - Result — the result of the CAPTCHA resolution.
2. **Parameters:** (required):
   - URL
   - URL API
   - API Key
   - Site key
   - Precision
   - Time-out

**ReCaptcha v3 specifics:** This type of CAPTCHA is based on a user's "humanity" rating (from 0.1 to 0.9). The API returns a rating value, and the site decides how to handle the request. To correctly solve the CAPTCHA, you need to find the `sitekey`, `action`, and the full URL of the page where the CAPTCHA needs to be solved.

### Solve question

Element for solving text-based CAPTCHAs:

1. **Output:**
   - Result — the result of the CAPTCHA resolution.
2. **Parameters:** (required):
   - URL API
   - Question
   - API Key
   - Time-out
   - Language

### Solve image

Element for solving image-based CAPTCHAs:

1. **Output:**
   - Result — the result of the CAPTCHA resolution.
2. **Parameters:** (required):
   - URL API
   - Image URL
   - Image
   - API Key
   - Time-out
   - Language

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).


