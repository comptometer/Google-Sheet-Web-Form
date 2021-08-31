# Google Sheet & WebForm
Save Web/HTML Form Data to Google Sheets

## Steps
### 1. Google Sheet
1. Goto [Google Sheet](https://docs.google.com/spreadsheets/u/0/) and create a blank sheet
2. Name the Fields as your need
3. go to <b>Tools > Script Editor</b>
4. Copy and paste the file [WebForm.gs](https://raw.githubusercontent.com/rpkc/WebForm/main/WebForm.gs) to the Script Editor
5. Change the `<SHEET_NAME>` with your sheet name 
6. deploy and copy the `deployment id`
### 2. Form (HTML)
```html
<script src="Relative/path/to/WebForm.js"></script>  <!-- Inside <head> -->
```
```html
<form method="post" autocomplete="off" name="contact">
      <input type="email" title="Type your email address" id="email" name="Email" placeholder="Your Email Address" required>
      <textarea id="message" title="Type your Message" name="Message" placeholder="Your Message ..." required></textarea>
      <input type="submit" title="Send your Message" value="Send">
</form>
```

### 3. Form (JS)
```js
document.addEventListener('submit',e=>{
    e.preventDefault(); //to stop the form being post
    var w = new WebForm(<DEPLOYMENT_ID>,<FORM_NAME>);//create an object
    w.submit(); // call to submit data
        })
```
#### *NB: 
1. Names of Form Elements should be as same as field names of Google Sheet<br>
2. All Names are case sensitive, It is recommended to make them in Block letter
<br>


# Caution
1. There are no Guarantee of Security
2. There are some [quotas](https://developers.google.com/apps-script/guides/services/quotas#current_quotas) of Google Sheet. So it is not for your next [Big Tech](https://en.wikipedia.org/wiki/Big_Tech) type website




