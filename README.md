1. Pre-requisites
     - Please refer requirements.txt file

2. Repo Information

1. Data Files
         1. data/data.json : contains training examples for the NLU model
         2. data/stories.md : contains training stories for the Core model
2. Model File
         1. contains trained (.tar) file
3. Script Files
         1. zomatopy : contains Zomato API integration code
         2. actions : contains the following custom actions (insert ZOMATO API key in this script file before starting RASA server)
		1. search restaurant
		2. validate location
		3. validate cuisine
		4. send email
		5. action restart
		6. reset slots
4. Config Files
         1. config.yml contains model configuration and custom policy
         2. credentials.yml contains authentication token to connect with channels like slack
         3. domain.yml defines chatbot domain like intents, entities, slots, templates, actions
         4. endpoints.yml contains the webhook configuration for custom action
         5. smtpconfig.txt contains SMTP server configuration information( for sending emails)
         6. cities.json contains list of Tier 1 and 2 cities

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
