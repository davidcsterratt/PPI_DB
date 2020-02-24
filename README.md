PPI_DB is a project to create and store Protein-Protein Interactions in the Kappa rule-based format.
For installation and usage please refer to the pdf report in
https://github.com/ayushdas/Thesis_Report .
This open source software code was developed in part or in whole in the Human Brain Project, 
funded from the European Union’s Horizon 2020 Framework Programme for Research and Innovation 
under the Specific Grant Agreement No. 785907 (Human Brain Project SGA2).

To deploy the web application onto a web server navigate to the django app folder within the project folder hosted on Github.
1. Navigate to the file django app/djangonautic/djangonautic/settings.py, update the database credentials with the ones created in the previous section, in the DATABASE section of the code and save it.
2. Navigate to the folder django app/djangonautic/ and run the following com- mands to synchronize the data models within the django application, with the database:
python manage.py migrate
python manage.py makemigrations
3. After synchronizing the data model, start the web server by running the follow- ing command:
python manage.py runserver
and acess the URLs for retrieving the PPIs based on agent name or domain names through a web browser.
The web application was tested on the web browsers Safari, Google Chrome and Mozilla Firefox.

In order to run the web application the following steps need to be performed:
1. The SQL server in which the database is hosted should be in running state. In MAC OSX this can be verified by navigating to the System Preferences → MySQL and ensuring that the MySQL server is running.
2. Navigate to the folder django app → djangonautic and run the following com- mand to start the server.
python manage.py runserver

Get PPI rules based on agent name
1. In order to access the PPI rules based on Agent Name, enter the following URL in the web browser: http://127.0.0.1:8000/ppi/AgentNameForm/.
2. Entertheagentnameinthetextboxprovidedandclickonsubmitasshowninthe figure 3.2. (Note: The agent name is case sensitive). Internally the django app makes a connection to the database and invokes the GetRulesFromAgentName stored procedure and passes the agent name as argument to it.
3. The retrieved PPI rules will be visible in the next page as shown in the figure 3.3. In case there are no matching PPI rules then a message is displayed on the screen to inform the user.
Get PPI rules based on domain names
1. In order to access the PPI rules based on a pair of domain names, enter the fol- lowing URL in the web browser: http://127.0.0.1:8000/ppi/DomainNameForm/
2. Enterthedomainnamesinthetextboxesprovidedandclickonsubmit,asshown in the figure 3.4. (Note: The domain names are case sensitive). Internally the django app makes a connection to the database and invokes the GetRulesFrom- DomainNamePair stored procedure and passes the domain names as arguments to it.
3. The retrieved PPI rules will be visible in the next page as shown in the figure 3.5. In case there are no matching PPI rules then a message is displayed on the screen to inform the user.
