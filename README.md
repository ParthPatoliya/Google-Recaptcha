# Google-Recaptcha
Applying Google recaptcha in php with server side validation and using site key and secret key with full details.


#Process
Register your site at Google reCAPTCHA
Submit HTML form
Get response key at server side
Re-verify the key and give response to user end.


Step 1: Register your site at Google reCAPTCHA — Register your website at Google reCAPTCHA platform to get keys i.e. Site key and Secret key needed to code the HTML form.

Click https://www.google.com/recaptcha/admin/create to go to Google reCAPTCHA website. 


Step 2: Creating Google reCAPTCHA form in HTML — Here, we are going to create a simple HTML form with action as action.php, one input field, and a button. Meanwhile, we need to add Google reCAPTCHA CDN link in our HTML document and a div tag in the form to get reCAPTCHA in the HTML document.

CDN Link: <script src=”https://www.google.com/recaptcha/api.js” async defer></script>

Div Tag: <div class=”g-recaptcha” data-sitekey=”your_site_key”></div> 

Note: You need to replace “your_site_key” with your Site Key.


Step 3: PHP Back end — We have successfully submitted the HTML form, now it’s time to code PHP back-end. After the submission of form, at the server-side, we are checking that the valid form is submitted or not by using the “isset()” function. After the validation, we fetched the name in $name variable and Google recaptcha response in $recaptcha variable.

Step 4: Verify the captcha – In order to verify the captcha, we need to make a post request to the following URL.

URL: https://www.google.com/recaptcha/api/siteverify?secret=<secret_key>&response=<response_key>
secret_key: This key you will get from Google console i.e. Secret Key.
response_key: This key comes from the client-side when a user submits the form.
g-recaptcha-response is the name of response key that browser will generate upon form submit. If its blank or null means user has not selected the captcha, so return the error.
Your need to replace “your_secret_key” with your Secret Key.
