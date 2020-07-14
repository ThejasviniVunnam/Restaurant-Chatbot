<!-- Stories 1 to 7: General search without any location, cuisine or budget input. Ex:show me restaurants-->
## story_01_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "299"}
    - slot{"budget": "299"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart

## story_02_searchvalid_with_noemail
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "Bangalore"}
    - slot{"location": "Bangalore"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Bangalore"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_03_locationinvalid_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "dehi"}
    - slot{"location": "dehi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "dlehi"}
    - slot{"location": "dlehi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
	
## story_04_locationinvalid_searchvalid_with_noemail
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "dehi"}
    - slot{"location": "dehi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "dlehi"}
    - slot{"location": "dlehi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_04_locationvalid_searchinvalid
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "299"}
    - slot{"budget": "299"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "invalid"}
    - utter_search_invalid
    - utter_goodbye
    - action_restart
	
## story_05_locationinvalid_searchinvalid
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "aga"}
    - slot{"location": "aga"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "agra"}
    - slot{"location": "agra"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "299"}
    - slot{"budget": "299"}
    - utter_searching
    - action_restaurant
    - slot{"location": "agra"}
    - slot{"search_validity" : "invalid"}
    - utter_search_invalid
    - utter_goodbye
    - action_restart
	
## story_06_locationvalid_cuisineinvalid_with_email
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "thai"}
    - slot{"cuisine": "thai"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "Chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "701"}
    - slot{"budget": "701"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Mumbai"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
	
## story_07_locationvalid_cuisineinvalid_no_email
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "thai"}
    - slot{"cuisine": "thai"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "Chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "701"}
    - slot{"budget": "701"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Mumbai"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart

<!-- Stories 8 to 18:Start with location info -->
## story_08_locationvalid_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search{"location": "chennai"}
    - slot{"location": "chennai"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "chennai"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_09_locationvalid_searchvalid_with_noemail
* greet
    - utter_greet
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "701"}
    - slot{"budget": "701"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_10_locationinvalid_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search{"location": "thirupathi"}
    - slot{"location": "thirupathi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Bangalore"}
    - slot{"location": "Bangalore"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Bangalore"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_11_locationinvalid_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search{"location": "thirupathi"}
    - slot{"location": "thirupathi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Bangalore"}
    - slot{"location": "Bangalore"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Bangalore"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart

## story_12_locationvalid_searchinvalid
* greet
    - utter_greet
* restaurant_search{"location": "chennai"}
    - slot{"location": "chennai"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "chennai"}
    - slot{"search_validity" : "invalid"}
    - utter_search_invalid
    - utter_goodbye
    - action_restart
	
<!-- no greet, start with location -->  
## story_13_locationvalid_searchvalid_with_email
* restaurant_search{"location": "chennai"}
    - slot{"location": "chennai"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "chennai"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_14_locationvalid_searchvalid_with_noemai
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "701"}
    - slot{"budget": "701"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
    
## story_15_locationinvalid_searchvalid_with_email
* restaurant_search{"location": "thirupathi"}
    - slot{"location": "thirupathi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Bangalore"}
    - slot{"location": "Bangalore"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Bangalore"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_16_locationinvalid_searchvalid_with_noemail
* restaurant_search{"location": "thirupathi"}
    - slot{"location": "thirupathi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Bangalore"}
    - slot{"location": "Bangalore"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Bangalore"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_17_locationvalid_cuisineinvalid_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search{"location": "chennai"}
    - slot{"location": "chennai"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "mexican"}
    - slot{"cuisine": "mexican"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "chennai"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_18_locationvalid_cuisineinvalid_searchvalid_with_noemail
* greet
    - utter_greet
* restaurant_search{"location": "chennai"}
    - slot{"location": "chennai"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "mexican"}
    - slot{"cuisine": "mexican"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "chennai"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
<!-- Stories 19 to 33 :Start with cuisine info -->
## story_19_cuisine_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "italian"}
    - slot{"cuisine": "italian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart

## story_20_cuisine_searchvalid_with_noemail
* greet
    - utter_greet
* restaurant_search{"cuisine": "american"}
    - slot{"cuisine": "american"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "pune"}
    - slot{"location": "pune"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "pune"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart

## story_21_cuisine_searchinvalid
* greet
    - utter_greet
* restaurant_search{"cuisine": "italian"}
    - slot{"cuisine": "italian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "invalid"}
    - utter_search_invalid
    - utter_goodbye
    - action_restart
	
## story_22_cuisineinvalid_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "japanese"}
    - slot{"cuisine": "japanese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "north indian"}
    - slot{"cuisine": "north indian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "vijayawada"}
    - slot{"location": "vijayawada"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "vijayawada"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_23_cuisineinvalid_searchvalid_with_no_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "japanese"}
    - slot{"cuisine": "japanese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "north indian"}
    - slot{"cuisine": "north indian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "vijayawada"}
    - slot{"location": "vijayawada"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "vijayawada"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
    
## story_24_cuisineinvalid_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "japanese"}
    - slot{"cuisine": "japanese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "north indian"}
    - slot{"cuisine": "north indian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "thiruvallur"}
    - slot{"location": "thiruvallur"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "vijayawada"}
    - slot{"location": "vijayawada"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "vijayawada"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_25_cuisineinvalid_searchvalid_with_no_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "japanese"}
    - slot{"cuisine": "japanese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "north indian"}
    - slot{"cuisine": "north indian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "thiruvallur"}
    - slot{"location": "thiruvallur"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "vijayawada"}
    - slot{"location": "vijayawada"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "vijayawada"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_26_cuisine_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "italian"}
    - slot{"cuisine": "italian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "thirupathi"}
    - slot{"location": "thirupathi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Shimla"}
    - slot{"location": "Shimla"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Shimla"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart

## story_27_cuisine_searchvalid_with_noemail
* greet
    - utter_greet
* restaurant_search{"cuisine": "italian"}
    - slot{"cuisine": "italian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "thirupathi"}
    - slot{"location": "thirupathi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Vellore"}
    - slot{"location": "Vellore"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Vellore"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart

<!-- no greet, start with cuisine -->
## story_28_cuisine_searchvalid_with_email
* restaurant_search{"cuisine": "italian"}
    - slot{"cuisine": "italian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_29_cuisine_searchvalid_with_email
* restaurant_search{"cuisine": "italian"}
    - slot{"cuisine": "italian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
    
## story_30_cuisineinvalid_searchvalid_with_email
* restaurant_search{"cuisine": "japanese"}
    - slot{"cuisine": "japanese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "north indian"}
    - slot{"cuisine": "north indian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "vijayawada"}
    - slot{"location": "vijayawada"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "vijayawada"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_31_cuisineinvalid_searchvalid_with_no_email
* restaurant_search{"cuisine": "japanese"}
    - slot{"cuisine": "japanese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "north indian"}
    - slot{"cuisine": "north indian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "vijayawada"}
    - slot{"location": "vijayawada"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "vijayawada"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
    
## story_32_cuisine_searchvalid_with_email
* restaurant_search{"cuisine": "italian"}
    - slot{"cuisine": "italian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "thirupathi"}
    - slot{"location": "thirupathi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Shimla"}
    - slot{"location": "Shimla"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Shimla"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart

## story_33_cuisine_searchvalid_with_noemail
* restaurant_search{"cuisine": "italian"}
    - slot{"cuisine": "italian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "thirupathi"}
    - slot{"location": "thirupathi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Vellore"}
    - slot{"location": "Vellore"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Vellore"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart

<!-- Stories 34 to 44:Start with location+cuisine info -->
## story_34_location_cuisine_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "italian", "location": "Chandigarh"}
    - slot{"cuisine": "italian"}
    - slot{"location": "Chandigarh"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Chandigarh"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_35_location_cuisine_searchvalid_with_noemail
* greet
    - utter_greet
* restaurant_search{"cuisine": "mexican", "location": "Patna"}
    - slot{"cuisine": "mexican"}
    - slot{"location": "Patna"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "700"}
    - slot{"budget": "700"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Patna"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_36_location_cuisine_searchinvalid
* greet
    - utter_greet
* restaurant_search{"cuisine": "italian", "location": "Chandigarh"}
    - slot{"cuisine": "italian"}
    - slot{"location": "Chandigarh"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Chandigarh"}
    - slot{"search_validity" : "invalid"}
    - utter_search_invalid
    - utter_goodbye
    - action_restart
    
## story_37_location_cuisine_invalid_retry_with_email
* greet
  - utter_greet
* restaurant_search{"location": "Mumbai", "cuisine": "french"}
    - slot{"cuisine": "french"}
    - slot{"location": "Mumbai"}
    - action_check_location
    - slot{"location_match" : "valid"}  
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "Chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "701"}
    - slot{"budget": "701"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Mumbai"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart

## story_38_location_cuisine_invalid_retry_no_email
* greet
  - utter_greet
* restaurant_search{"location": "agra", "cuisine": "thai"}
    - slot{"cuisine": "thai"}
    - slot{"location": "agra"}
    - action_check_location
    - slot{"location_match" : "valid"}  
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "mexican"}
    - slot{"cuisine": "mexican"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "700"}
    - slot{"budget": "700"}
    - utter_searching
    - action_restaurant
    - slot{"location": "agra"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
    
<!-- no greet, location + cuisine --> 
 ## story_39_location_cuisine_searchvalid_with_noemail
* restaurant_search{"cuisine": "south indian", "location": "Purulia"}
    - slot{"cuisine": "south indian"}
    - slot{"location": "Purulia"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "700"}
    - slot{"budget": "700"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Purulia"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
    
## story_40_location_cuisine_searchvalid_with_email
* restaurant_search{"cuisine": "north indian", "location": "Sangli"}
    - slot{"cuisine": "north indian"}
    - slot{"location": "Sangli"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Sangli"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_41_location_cuisine_invalid_retry_no_email
* restaurant_search{"location": "agra", "cuisine": "thai"}
    - slot{"cuisine": "thai"}
    - slot{"location": "agra"}
    - action_check_location
    - slot{"location_match" : "valid"}  
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "mexican"}
    - slot{"cuisine": "mexican"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "700"}
    - slot{"budget": "700"}
    - utter_searching
    - action_restaurant
    - slot{"location": "agra"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
    
## story_42_location_cuisine_invalid_retry_with_email
* restaurant_search{"location": "Bijapur", "cuisine": "french"}
    - slot{"cuisine": "spanish"}
    - slot{"location": "Bijapur"}
    - action_check_location
    - slot{"location_match" : "valid"}  
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "Chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "701"}
    - slot{"budget": "701"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Bijapur"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
<!-- cuisine + location, both invalid -->
## story_43_locationinvalid_cuisine_invalid_retry_with_email
* greet
  - utter_greet
* restaurant_search{"location": "dlehi", "cuisine": "thai"}
    - slot{"cuisine": "thai"}
    - slot{"location": "dlehi"}
    - action_check_location
    - slot{"location_match": "invalid"} 
    - utter_location_not_found
* restaurant_search{"location": "Bangalore"}
    - slot{"location": "Bangalore"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "mexican"}
    - slot{"cuisine": "mexican"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "700"}
    - slot{"budget": "700"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Bangalore"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_44_locationinvalid_cuisine_invalid_retry_no_email
* greet
  - utter_greet
* restaurant_search{"location": "dlehi", "cuisine": "thai"}
    - slot{"cuisine": "thai"}
    - slot{"location": "dlehi"}
    - action_check_location
    - slot{"location_match": "invalid"} 
    - utter_location_not_found
* restaurant_search{"location": "Bangalore"}
    - slot{"location": "Bangalore"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "mexican"}
    - slot{"cuisine": "mexican"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "700"}
    - slot{"budget": "700"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Bangalore"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart	

<!-- Stories 45 to 50:Start with location+budget info -->
## story_45_location_budget_with_email
* greet
    - utter_greet
* restaurant_search{"location": "delhi", "budget": "1000"}
    - slot{"location": "delhi"}
    - slot{"budget": "1000"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
	
## story_46_location_budget_with_noemail
* greet
    - utter_greet
* restaurant_search{"location": "delhi", "budget": "1000"}
    - slot{"location": "delhi"}
    - slot{"budget": "1000"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_47_locationinvalid_budget_with_email
* greet
    - utter_greet
* restaurant_search{"location": "rishikesh", "budget": "1000"}
    - slot{"location": "rishikesh"}
    - slot{"budget": "1000"}
    - action_check_location
    - slot{"location_match": "invalid"} 
    - utter_location_not_found
* restaurant_search{"location": "Erode"}
    - slot{"location": "Erode"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Erode"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
	
## story_48_locationinvalid_budget_with_noemail
* greet
    - utter_greet
* restaurant_search{"location": "rishikesh", "budget": "1000"}
    - slot{"location": "rishikesh"}
    - slot{"budget": "1000"}
    - action_check_location
    - slot{"location_match": "invalid"} 
    - utter_location_not_found
* restaurant_search{"location": "Erode"}
    - slot{"location": "Erode"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Erode"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_49_location_budget_searchinvalid
* greet
    - utter_greet
* restaurant_search{"location": "delhi", "budget": "1000"}
    - slot{"location": "delhi"}
    - slot{"budget": "1000"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "invalid"}
    - utter_search_invalid
    - utter_goodbye
    - action_restart
	
## story_50_locationinvalid_budget_searchinvalid
* greet
    - utter_greet
* restaurant_search{"location": "rishikesh", "budget": "1000"}
    - slot{"location": "rishikesh"}
    - slot{"budget": "1000"}
    - action_check_location
    - slot{"location_match": "invalid"} 
    - utter_location_not_found
* restaurant_search{"location": "Erode"}
    - slot{"location": "Erode"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "invalid"}
    - utter_search_invalid
    - utter_goodbye
    - action_restart
	
<!-- Stories 51 to 56:Start with cuisine+budget info -->
## story_51_cuisine_budget_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "chinese", "budget": "1000"}
    - slot{"cuisine": "chinese"}
    - slot{"budget": "1000"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
	
## story_52_cuisine_budget_with_noemail
* greet
    - utter_greet
* restaurant_search{"cuisine": "chinese", "budget": "1000"}
    - slot{"cuisine": "chinese"}
    - slot{"budget": "1000"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_53_cuisineinvalid_budget_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "spanish", "budget": "200"}
    - slot{"cuisine": "spanish"}
    - slot{"budget": "200"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "north indian"}
    - slot{"cuisine": "north indian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "vijayawada"}
    - slot{"location": "vijayawada"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "vijayawada"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
	
## story_54_cuisineinvalid_budget_with_noemail
* greet
    - utter_greet
* restaurant_search{"cuisine": "spanish", "budget": "200"}
    - slot{"cuisine": "spanish"}
    - slot{"budget": "200"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "north indian"}
    - slot{"cuisine": "north indian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "vijayawada"}
    - slot{"location": "vijayawada"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "vijayawada"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_55_cuisine_budget_searchinvalid
* greet
    - utter_greet
* restaurant_search{"cuisine": "chinese", "budget": "1000"}
    - slot{"cuisine": "chinese"}
    - slot{"budget": "1000"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "invalid"}
    - utter_search_invalid
    - utter_goodbye
    - action_restart
	
## story_56_cuisineinvalid_budget_searchinvalid
* greet
    - utter_greet
* restaurant_search{"cuisine": "spanish", "budget": "200"}
    - slot{"cuisine": "spanish"}
    - slot{"budget": "200"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "north indian"}
    - slot{"cuisine": "north indian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* restaurant_search{"location": "vijayawada"}
    - slot{"location": "vijayawada"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "vijayawada"}
    - slot{"search_validity" : "invalid"}
    - utter_search_invalid
    - utter_goodbye
    - action_restart
	
<!-- Stories 57 to 65:Start with location+cuisine+budget info -->	
## story_57_location_cuisine_budget_given_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "chinese", "location": "delhi", "budget": "299"}
    - slot{"cuisine": "chinese"}
    - slot{"location": "delhi"}
    - slot{"budget": "299"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_58_location_cuisine_budget_given_noemail
* greet
    - utter_greet
* restaurant_search{"cuisine": "chinese", "location": "delhi", "budget": "299"}
    - slot{"cuisine": "chinese"}
    - slot{"location": "delhi"}
    - slot{"budget": "299"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_59_locationinvalid_cuisine_budget_given_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "chinese", "location": "kadapa", "budget": "299"}
    - slot{"cuisine": "chinese"}
    - slot{"location": "kadapa"}
    - slot{"budget": "299"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Meerut"}
    - slot{"location": "Meerut"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Meerut"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_60_locationinvalid_cuisine_budget_given_noemail
* greet
    - utter_greet
* restaurant_search{"cuisine": "chinese", "location": "kadapa", "budget": "299"}
    - slot{"cuisine": "chinese"}
    - slot{"location": "kadapa"}
    - slot{"budget": "299"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Meerut"}
    - slot{"location": "Meerut"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Meerut"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_61_locationvalid_cuisineinvalid_budget_given_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "japanese", "location": "Moradabad", "budget": "299"}
    - slot{"cuisine": "japanese"}
    - slot{"location": "Moradabad"}
    - slot{"budget": "299"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "mexican"}
    - slot{"cuisine": "mexican"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Moradabad"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_62_locationvalid_cuisineinvalid_budget_given_noemail
* greet
    - utter_greet
* restaurant_search{"cuisine": "japanese", "location": "Moradabad", "budget": "299"}
    - slot{"cuisine": "japanese"}
    - slot{"location": "Moradabad"}
    - slot{"budget": "299"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "mexican"}
    - slot{"cuisine": "mexican"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Moradabad"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_63_locationinvalid_cuisineinvalid_budget_given_with_email
* greet
    - utter_greet
* restaurant_search{"cuisine": "french", "location": "kadapa", "budget": "299"}
    - slot{"cuisine": "french"}
    - slot{"location": "kadapa"}
    - slot{"budget": "299"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Meerut"}
    - slot{"location": "Meerut"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "american"}
    - slot{"cuisine": "american"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Meerut"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
    
## story_64_locationinvalid_cuisineinvalid_budget_given_noemail
* greet
    - utter_greet
* restaurant_search{"cuisine": "french", "location": "kadapa", "budget": "299"}
    - slot{"cuisine": "french"}
    - slot{"location": "kadapa"}
    - slot{"budget": "299"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "Meerut"}
    - slot{"location": "Meerut"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "american"}
    - slot{"cuisine": "american"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Meerut"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* deny
    - utter_no_email_sent
    - action_restart
	
## story_65_location_cuisine_budget_searchinvalid
* greet
    - utter_greet
* restaurant_search{"cuisine": "chinese", "location": "delhi", "budget": "299"}
    - slot{"cuisine": "chinese"}
    - slot{"location": "delhi"}
    - slot{"budget": "299"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "invalid"}
    - utter_search_invalid
    - utter_goodbye
    - action_restart
	
<!-- miscellaneous -->
## story_66_greet_goodbye
* greet
    - utter_greet
* goodbye
    - utter_goodbye
    - action_restart

## story_67_leave_in_between
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* goodbye
    - utter_goodbye
    - action_restart
    
## story_68_leave_in_between
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "mexican"}
    - slot{"cuisine": "mexican"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "399"}
    - slot{"budget": "399"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* goodbye
    - utter_goodbye
    - action_restart
    
## story_69_leave_in_between
* greet
    - utter_greet
* restaurant_search{"cuisine": "chinese", "location": "mumbai"}
    - slot{"cuisine": "chinese"}
    - slot{"location": "mumbai"}
    - action_check_location
    - slot{"location_match": "valid"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* goodbye
    - utter_goodbye
    - action_restart
    
## story_70_leave_in_between
* greet
    - utter_greet
* restaurant_search{"cuisine": "italian"}
    - slot{"cuisine": "italian"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_location
* goodbye
    - utter_goodbye
    - action_restart

## story_71_invalidlocation_goodbye
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "delhsdadi"}
    - slot{"location": "delhsdadi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* deny
    - utter_goodbye
    - action_restart
    
## story_72_invalidlocation_goodbye
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "dehi"}
    - slot{"location": "dehi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* restaurant_search{"location": "dlehi"}
    - slot{"location": "dlehi"}
    - action_check_location
    - slot{"location_match": "invalid"}
    - utter_location_not_found
* goodbye
    - utter_goodbye
    - action_restart
    
## story_73_say_goodbye
* goodbye
  - utter_goodbye
  
<!-- Stories 74 to :email is provided without prompt -->	  
## story_74_searchvalid_with_email
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "299"}
    - slot{"budget": "299"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
	
## story_75_locationvalid_cuisineinvalid_with_email
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "thai"}
    - slot{"cuisine": "thai"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "invalid"}
    - utter_cuisine_invalid
    - utter_ask_cuisine
* restaurant_search{"cuisine": "Chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "701"}
    - slot{"budget": "701"}
    - utter_searching
    - action_restaurant
    - slot{"location": "Mumbai"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart
	
## story_76_searchvalid_with_email_without_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"location_match": "valid"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_cuisine_valid
    - slot{"cuisine_validity" : "valid"}
    - utter_ask_budget
* restaurant_search{"budget": "299"}
    - slot{"budget": "299"}
    - utter_searching
    - action_restaurant
    - slot{"location": "delhi"}
    - slot{"search_validity" : "valid"}
    - utter_ask_for_email_to_send
* affirm
    - utter_ask_email_address
* send_email{"email": "abcdef@gmail.com"}
    - slot{"email": "abcdef@gmail.com"}
    - action_send_email
    - utter_email_sent
    - action_restart	