1. Pre-requisites
     - Please refer requirements.txt file under casestudy folder

2. Repo Information

   Data Files
         - data/data.json : contains training examples for the NLU model
         - data/stories.md : contains training stories for the Core model
  Model File
         - contains trained (.tar) file
   Script Files
         - zomatopy : contains Zomato API integration code
         - actions : contains the following custom actions (insert ZOMATO API key in this script file before starting RASA server)
	-- search restaurant
	-- validate location
	-- validate cuisine
	-- send email
	-- action restart
	-- reset slots
   Config Files
         - config.yml contains model configuration and custom policy
         - credentials.yml contains authentication token to connect with channels like slack
         - domain.yml defines chatbot domain like intents, entities, slots, templates, actions
         - endpoints.yml contains the webhook configuration for custom action
         - smtpconfig.txt contains SMTP server configuration information( for sending emails)
         - cities.json contains list of Tier 1 and 2 cities

3. Steps to run the chatbot on command prompt

     1. Open cmd, Go to “cd C:\”
     2. Open virtual env- “.\venv\Scripts\activate”
     3. Go to case study folder- cd “C:\Users\thejasvini\Desktop\casestudy”
     4. Give the cmd rasa train. This will train both nlu and core and create training file under models folder
         (venv) C:\Users\thejasvini\Desktop\casestudy>rasa train
     5. Run RASA action server
         (venv) C:\Users\thejasvini\Desktop\casestudy>rasa run actions
     6. Once the Action endpoint is up and running on http://localhost:5055, Open another cmd and repeat steps 1 to 3
     7. Now chat with the bot using the cmd- rasa shell
