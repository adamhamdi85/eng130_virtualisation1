### How to reverse proxy
- copy and paste `sudo nano /etc/nginx/sites-available/default` into your virtual machine terminal.
- press enter then in the location part delete whats inside and add
        `proxy_pass http://localhost:8080;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;`
- then change '8080' then to '3000' and make sure the intendation is correct
- after this run `sudo nginx -t` in the terminal to check the syntax to ensure there are no errors
- Next, restart Nginx by doing this `sudo systemctl restart nginx`.
- `npm install` then `npm start` to run the virtual machine
- Now add your ip address into the browser without the '3000' and the app will run smoothly.