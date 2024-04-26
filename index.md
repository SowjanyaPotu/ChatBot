<html>
  <body>
    <script type='text/javascript'>
    function initEmbeddedMessaging() {
        try {
            embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'
            
            window.addEventListener("onEmbeddedMessagingReady", () => {
    console.log("Received the onEmbeddedMessagingReady event…");
    embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
	"Customer_First_Name" : "FirstName_fromWebsite",
	"Customer_Last_Name" : "Lastname_fromWebsite",
	"Customer_Email_Address" : "Test123@fromWebsite.com",
	"Customer_Language_Preference" : "English"}
	);
});

            embeddedservice_bootstrap.init(
                '00D04000000p5i3',
                'UL_Digital_Assistant',
                'https://ulenterpriseorg--chatbot.sandbox.my.site.com/ESWULDigitalAssistant1707752748287',
                {
                    scrt2URL: 'https://ulenterpriseorg--chatbot.sandbox.my.salesforce-scrt.com'
                }
            );
        } catch (err) {
            console.error('Error loading Embedded Messaging: ', err);
        }
    };
</script>
<script type='text/javascript' src='https://ulenterpriseorg--chatbot.sandbox.my.site.com/ESWULDigitalAssistant1707752748287/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
  </body>
</html>
