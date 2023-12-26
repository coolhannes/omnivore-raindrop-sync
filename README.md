# omnivore-raindrop-sync
Forked from [unappendixed/omnivore-raindrop-sync](https://github.com/unappendixed/omnivore-raindrop-sync). This automatically syncs Omnivore pages to Raindrop.io. This fork is optimized for a hosted version on Render, which offers free [web service hosting](https://docs.render.com/web-services).

## Setup

1. Go to https://app.raindrop.io/settings/integrations. Create a new app at the bottom of the page and create a test token in the pop-up window. Save the text token for later (we don't need a real token since this is for personal use only).
2. Get your Omnivore user ID. Your Omnivore user id can either be found in the body of the webhook request or by checking the localStorage of the Omnivore app (run `localStorage.getItem("ajs_user_traits")` in the dev console while Omnivore is open) in your browser.
3. Sign up on render.com and select "New > Web Service" in the top of the tool. Select "Build and deploy from a Git repository", and then scroll down to "Public Git repository" and enter the URL to this directory. Give it a name, ignore the settings until you can pick "Free" and then keep scrolling to *Environment Variables*. Create two variables: "RAINDROP_TOKEN", set to the value you copied in #1, and "OMNIVORE_USERID", set to the value you copied in #2. 
5. Hit create, and then it should take you to the webservice page. It should auto-deploy which might take a second. At the top, there will be a URL you can copy like "https://YOUR-APP-NAME.onrender.com", copy it.
6. Go to https://omnivore.app/settings/webhooks and add a webhook pointing to the URL you just copied.

After this set up, when you add a link to Omnivore, it should also automatically populate in your "Unsorted" folder in Raindrop!
