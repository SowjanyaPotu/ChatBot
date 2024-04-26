<html>
  <body>
	  <button id="launchChatButton" onclick="launchChat()">Click to contact support</button>
    <script type='text/javascript'>
    function initEmbeddedMessaging() {
        try {
            embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'
            
            window.addEventListener("onEmbeddedMessagingReady", () => {
    console.log("Received the onEmbeddedMessagingReady event…");
    embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
	"Customer_First_Name" : "FirstName_fromgithub",
	"Customer_Last_Name" : "Lastname_fromgithub",
	"Customer_Email_Address" : "Test123@fromgithub.com",
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
// Call Launch Chat API.
<script>
    function launchChat() {
	//initEmbeddedMessaging();
        embeddedservice_bootstrap.utilAPI
	    .launchChat()
            .then(() => {
                // Success handler used to perform actions
                // when the chat client launches successfully.
                // For example, create a method that disables the launch chat button.
              //  disableLaunchChatButton();
            }).catch(() => {
                // Error handler used to perform actions
                // if the chat client fails to launch.
                // For example, create a method that hides the launch chat button.
             //   hideLaunchChatButton();
            }).finally(() => {
                // Finally handler used to perform any clean-up actions
                // regardless of whether the chat client launches successfully or not.
                // For example, create a method that logs the user’s attempt to chat.
               // logEndUserAttemptToChat();
            });
    }
</script>

  </body>
</html>
