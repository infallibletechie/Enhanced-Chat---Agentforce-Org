<html>
    <script type='text/javascript'>
    	function initEmbeddedMessaging() {
    		try {
    			embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

                window.addEventListener("onEmbeddedMessagingSessionStatusUpdate", (event) => {
                    console.log("START:: Status Update");
                
                    const tempContent = event.detail;
                    console.log(JSON.stringify(tempContent));
                    const sessionData = JSON.parse(tempContent.conversationEntry.entryPayload);

                    if (
                        sessionData.sessionStatus === "Ended" &&
                        sessionData.sessionStatusPrev === "Active" && 
                        sessionData..sessionEndedByRole === 'Agent' 
                    ) {
                        console.log("Active Session ended");
                        embeddedservice_bootstrap.userVerificationAPI
                        .clearSession()
                        .then(() => {
                            console.log("Session cleared successfully.");
                        })
                        .catch((error) => {
                            console.error("Error clearing session:", error);
                        })
                        .finally(() => {
                            console.log("clearSession finally.");
                            window.alert("Agent Ended the Chat!!!");
                        });
                    }
                    
                    console.log("END:: Status Update");
                });
    
    			embeddedservice_bootstrap.init(
    				'00DKj00000BqFBw',
    				'Enhanced_Chat',
    				'https://mduraipand-250112-382-demo.my.site.com/ESWEnhancedChat1763259170654',
    				{
    					scrt2URL: 'https://mduraipand-250112-382-demo.my.salesforce-scrt.com'
    				}
    			);
    		} catch (err) {
    			console.error('Error loading Embedded Messaging: ', err);
    		}
    	};
    </script>
    <script type='text/javascript' src='https://mduraipand-250112-382-demo.my.site.com/ESWEnhancedChat1763259170654/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
</html>
