# KOTournament

## What will it do?

* Generates the bracket(s) for single, double and triple Knockout tournaments
* Auto scheduling with game times and available playing fields (like RRSchedule)
* Output a graphical representation of the tournament (probably with html5 and jquery)
* Attach team name, game info, and game result (if applicable) to each node
* Provides JSON import/export to easily recreate a tournament

The use case I have in mind is someone who:

1) Generate tournament brackets with the gem (ask tournament type, number of teams, game times, etc)
2) Store the tournament (JSON) in a database 
3) Whenever we want to display the tournament, we pass the JSON to the gem
4) This will output the tournament in HTML5+Jquery

To advance the tournament (indicating the winner of some node), it could work this way:

* The user enter his game results somehow in his application (nothing to do with us)
* Then he call the gem by passing the actual JSON stored in his database
* Then he call a method like "kot.advance(node, winner, game_results, ...)" 
* The JSON will be updated and returned to the user
* The user store the new JSON in the database 
* Now if we want to display the tournament, the JSON is up to date!
