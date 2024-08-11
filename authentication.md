## Authentication  
 

When using the General Putnam Motel Diner API to order the burger meal, the user authenticates using the one step OAuth2 password grant. They need to log in using a username and password issued by the GPMD within the last 6 months. Each account must have a valid credit card and payment plan in place. After the user successfully provides a valid username and password, the API makes a POST request to the server and grants the user a token to access to the GPMD menu.  
