<html>

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Chat Input Example</title>
	<style>
	body {
		font-family: Arial, sans-serif;
		background-color: #f7f8fa;
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100vh;
		margin: 0;
	}

	.chat-container {
		background: #fff;
		border: 1px solid #ddd;
		border-radius: 10px;
		width: 400px;
		padding: 16px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
		display: flex;
		flex-direction: column;
	}

	.chat-input-area {
		display: flex;
		border: 1px solid #ccc;
		border-radius: 20px;
		padding: 8px 12px;
		background: #f1f1f1;
	}

	.chat-input {
		flex: 1;
		border: none;
		background: transparent;
		outline: none;
		font-size: 16px;
		padding: 6px;
	}

	.send-button {
		background-color: #0078ff;
		border: none;
		color: white;
		border-radius: 50%;
		width: 36px;
		height: 36px;
		cursor: pointer;
		font-size: 16px;
		display: flex;
		align-items: center;
		justify-content: center;
		transition: background 0.2s;
	}

	.send-button:hover {
		background-color: #005fd1;
	}

	/* --- CSS for Styling the Button --- */
	.send-message-button {
		/* Background and Dimensions */
		background-color: #00008b;
		/* A deep blue, similar to the image */
		color: white;
		/* White text */
		padding: 15px 30px;
		/* Padding for height and width */
		font-size: 18px;
		/* Readable text size */
		font-weight: bold;
		cursor: pointer;
		/* Changes mouse to a pointer on hover */
		border: none;
		/* Remove default button border */
		display: inline-block;
		/* Allows setting padding/margin */
		text-align: center;
		border-radius: 5px;
		/* Slight rounding of corners */
		/* The White Border/Outline Effect */
		box-shadow: 0 0 0 2px white;
		/* A 2px white "stroke" */
		outline: 2px solid #00008b;
		/* Helps create the gap/depth effect */
	}

	.send-message-button:hover {
		background-color: #0000a0;
		/* Slightly lighter blue on hover */
	}

	<script type='text/javascript'>function initEmbeddedMessaging() {
		try {
			embeddedservice_bootstrap.settings.language='en_US'; // For example, enter 'en' or 'en-US'
			// Hiding Chat Button on page load
			embeddedservice_bootstrap.settings.hideChatButtonOnLoad=true;

			/* START:: Conversation Opened Listener */
			window.addEventListener("onEmbeddedMessagingConversationOpened", (event)=> {
				hideChatContainer();
			});
			/* END:: Conversation Opened Listener */
			
			/* START:: Conversation Closed Listener */
			window.addEventListener("onEmbeddedMessagingWindowClosed", (event)=> {
				showChatContainer();
			});

			/* END:: Conversation Closed Listener */
			/* START:: Button Created Listener */
			window.addEventListener("onEmbeddedMessagingButtonCreated", (event)=> {
				showChatContainer();
			});
			/* END:: Button Created Listener */
			
			embeddedservice_bootstrap.init('00DKj00000BqFBw',
			'Enhanced_Chat',
			'https://mduraipand-250112-382-demo.my.site.com/ESWEnhancedChat1763259170654',
				{
				scrt2URL: 'https://mduraipand-250112-382-demo.my.salesforce-scrt.com'
			}

			);
		}

		catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	}

	</script><script type='text/javascript'src='https://mduraipand-250112-382-demo.my.site.com/ESWEnhancedChat1763259170654/assets/js/bootstrap.min.js'onload='initEmbeddedMessaging()'></script>
	</style>

<body>
	<div class="chat-container">
		<div> Welcome to our Chat!!! <br /><br /><br />
		</div>
		<div class="chat-input-area">
			<input type="text" id="chatInput" class="chat-input" placeholder="Type a message..." />
			<button class="send-button" id="sendBtn">➤</button>
		</div>
		<div>
			<br /><br />
			<button class="send-message-button" id="orderButton"> Need help with my Order </button>
			<br /><br />
			<button class="send-message-button" id="caseButton"> Need help with my Case </button>
		</div>
	</div>
</body>

</html>
