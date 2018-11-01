# Week 8 Assignment  

### Blue
1.Session Hijacking:
 I loged in on one window and use developer tools to copy the session id. In another window, I  useed the tool provided to change session id to the one copied from victim.	




2.  SQL injection:
In the url public/staff/salespeople/show.php?id=??, I injected the sql code ' or sleep (6)=0--' instead of the user id. This makes the page hold for 6 seconds because the database is paused for 6 seconds.


### Green
3. Username enumeration
I tried using a correct username with a wrongpassword, and a incorrect name with wrong password. A correct username shows as bold while and incorrect username shows a a regular when trying to login. This reveals the valid usernames.

4. XSS
Script can be inserted in the feedback box of the contact us. I inserted a <IMG SRC=javascript:alert('XSS')> script. When log in as admin and check feedback the script runs showing an alert.




### Red:
5. IDOR
The url public/salesperson.php?id=?? uses enumerated user ids. I kept trying different numbers until I got to id 10 which is supposed to be private. The developers believed that not giving a link to this user would be enough but they also should hava blocked access to this user information.

 6. CSRF
I created an html page which tricks an admin into clicking submit. The html sends the action "https://35.184.88.145/red/public/staff/salespeople/edit.php?id=6" to  modify the user information when the admin who is logged in clicks submit on my page. In my page I include hidden input tags to change first_name, last_name, phone, and email.
