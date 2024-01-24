# Better superset
This repo took the famous superset modified the code a little bit to add extra customizations to the original superset.

You can read the original docs from [HERE](./ORIGINALREADME.md)

# [BACKEND]
- install py 3.11.5 https://www.python.org/downloads/release/python-3115/

- create py env using the following commands
  ```bash
    py -m venv .your_env_name
  ```
 
- Activate the env using
  ```bash
    .your_env_name\Scripts\activate
  ```
 
- Use the following commands
    ``` bash
    pip install -r requirements/testing.txt
    ```
    ```bash
    pip install -e .
    ```

- go to ./superset/config.py  and search for key "SECRET_KEY" and change the old value with any seceret string ex: "ABC@#123"

- Use the following commands
    ```bash
    superset db upgrade
    ```
    ```bash
    superset fab create-admin
    ```
 
- Follow the steps in creating user named admin with password admin  [DO NOT CHANGE THE USER NAME admin THIS MIGHT LEAD TO ERRORS. YOU CAN MAKE OTHER USERS LATER]

- Use the following commands:
    ``` bash
    superset init
    ```
    ```bash
    superset load-examples
    ```

- Final step in backend server is to start the server:
  ```bash
    superset run -p 8088 --with-threads --reload --debugger --debug
  ```
 
TO OPEN THE SERVER AGAIN AFTER INIT INSTALLATION YOU HAVE TO ACTIVATE ENV AND RUN THE START COMMAND ONLY:
    ```bash
    .your_env_name\Scripts\activate
    ```
    ```bash
    superset run -p 8088 --with-threads --reload --debugger --debug
    ```
 


# [FRONTEND]

- install node 16 with npm 7  i recommend using NVM to do this https://github.com/coreybutler/nvm-windows
    ```bash
    cd superset-frontend
    ```
    ```bash
    npm ci
    ```
    ```bash
    npm i @react-spring/web global-box just-handlebars-helpers currency-formatter
    ```
- open this file superset-frontend/node_modules/just-handlebars-helpers/lib/helpers/formatters.js
- change line 27 require('currencyformatter.js');  to require('currency-formatter');
- to start the front-end server run:
    ```bash
    npm run dev-server
    ```
- open localhost:8000


# Styling Notes
 - there are some ant classes that you need to add styles to in the code
 - Always find the correct place to add styles.



