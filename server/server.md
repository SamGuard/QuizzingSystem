How to use the server sockets

Start
To start the connection just do a normal socket init once connected (socket.onopen event) send a setid which will set
the way the server identifies the client. 

Joining a team
Send a socket event with the purp jointeam with the data.code = the team code, and then data.name = the team name and
data.playerNames (these are optional, only needed if this is the first time someone is joining this team)

Getting Question
send a message with purp getquest to get the round and question. Round 0 will be returned if the game hasnt started
and question 0 will be returned if the round hasnt started.

Answering
All you do is send the answer with the purp of "submit" and then set data.answer to the answer and data.code = team code



How to use the API
For controlling the game, send a post request to /control. In the body there must be two thing:
secret = *ask me for the secret word*
command = next, prev, open or close

if you do not send the secret the request will just be rejected, dont try looking in the code for the secret as the
plain text is not in there only the sha256 shifted text is in there.

Send a post request to /answers to get all the answers people gave (with secret)
Send a post requets to /mark with the team code, the round, the question number and whether they got it right

