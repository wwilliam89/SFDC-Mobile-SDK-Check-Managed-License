#Simple Demo SFDC Mobile SDK App Verifying Managed Package License.

# Setup
<p>
This is a modified sample contact app from SFDC Mobile SDK 2.0. 
What's different?
</p>
Better mobile UI - Using Bootstrap
* Added License Checking logic.
  - If the user is licensed, show full feature set
  - If the user is not licensed, show reduced features.

Please add this apex code snippet into your managed package:
<pre><code>
@RestResource(urlMapping='/islicensed/*')
global with sharing class licenseRest {

  
  @HttpGet
    global static String doPost() {
       Boolean islicensed = System.Userinfo.isCurrentUserLicensed('WYProjectY');
       //replace WYProjectY with your managed package namespace
        if(islicensed)
            return 't';
        else
            return 'f';    
        
    }
}

</code></pre>






*Disclaimer, this is not supported officially, and does not guarantee to always work.
