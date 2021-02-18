Step 1 – open this site of Google to make a new secret Recaptcha
  https://www.google.com/recaptcha/admin/create
  
  Label:
  in this part write your faviorate name
  
  in this part(reCAPTCHA type) choose reCAPTCHA v3
  
  in this part(Domains) write somethings like localhost.



Step 2 – write in terminal:
 composer require biscolab/laravel-recaptcha
 
Step 3 – write in terminal:
  php artisan vendor:publish --provider="Biscolab\ReCaptcha\ReCaptchaServiceProvider"


step 4 - open config/recaptcha.php

change v2 to v3
 
 
Step 5 – Add the below code in .env
  RECAPTCHA_SITE_KEY=ADD_YOUR_SITE_KEY
  RECAPTCHA_SECRET_KEY=ADD_YOUR_SECRET_KEY
  


step 6 - write in terminal

 php artisan config:cache


step 7 - write the below code in head of template
<!DOCTYPE html>
<html>
    <head>
        ...
        ...
        {!! htmlScriptTagJsApi() !!}
    </head>




step 8 -  or you can write the belowe code
<script type="text/javascript">
function callbackThen(response){
    // read HTTP status
    console.log(response.status);
 
    // read Promise object
    response.json().then(function(data){
        console.log(data);
    });
}
function callbackCatch(error){
    console.error('Error:', error)
}
</script>
 
{!! htmlScriptTagJsApi([
    'callback_then' => 'callbackThen',
    'callback_catch' => 'callbackCatch'
]) !!}
  
  

 
						


 thanks  dont forget to subscribe
