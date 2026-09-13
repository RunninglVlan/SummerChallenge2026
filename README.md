# CodinGame Summer Challenge 2026 BackTrackKing CLI runner

This is a referee for CodinGame's Summer Challenge 2026 with command line interface adapted for usage with [cg-brutaltester](https://github.com/dreignier/cg-brutaltester)

https://www.codingame.com/contests/summer-challenge-2026-back-track-king

## Build

- Install Java 17 (JDK) and Maven
- Run `mvn clean package` in the root dir where pom.xml file is

The compiled jar file is in ./target/summer-challenge-2026-back-track-king-1.0-SNAPSHOT.jar

## Run

Get cg-brutaltester from Releases or by building as described in its README ([cg-brutaltester](https://github.com/dreignier/cg-brutaltester))

You can copy both referee and cg-brutaltester JAR files, i.e. summer-challenge-2026-back-track-king-1.0-SNAPSHOT.jar and cg-brutaltester-1.0.0.jar, to the same directory to make handling paths easier.

This is a sample command that works, you can change options as described in the cg-brutaltester README. Note: JAR names are shortened for simplicity.

```
java -jar cg-brutaltester.jar -r "java -jar summer-referee.jar" -p1 "new\Bot.exe" -p2 "python config\level2\Boss.py" -t 2 -n 10
```
Negative score for opponent is OK here, because we win just by completing the objective.

Use `-league 3` to run Bronze league logic - without tutorial objectives.

```
java -jar cg-brutaltester.jar -r "java -jar summer-referee.jar -league 3" -p1 "new\Bot.exe" -p2 "python config\level2\Boss.py" -t 2 -n 10
```

## See the replay of failed game

When there's an issue with a game, cg-brutaltester will show you the command to start web-server and see the replay. It can look like this:
```
java -jar summer-referee.jar -p1 new\Bot.exe -p2 python config\level2\Boss.py -s -d
seed=-6047263144251189400
```
Modify it a bit and run:
```
java -jar summer-referee.jar -p1 new\Bot.exe -p2 python config\level2\Boss.py -s -seed -6047263144251189400
```
Referee then will show web-server link where you can see the replay.

## How to fix black rectangle in web-server

After starting referee with `-s` option, web-server will be started and referee will show its local folder.
For some reason asset paths are broken and the viewer just shows black rectangle, so a temporary fix is to just copy everything that's in /assets folder, create one more /assets folder inside it and paste everything there.

## See the replay of any game

When the web-server is running, you can make it replay any of your games, just copy the desired game.json from the logs (that can be generated with `-l` option, e.g., `-l "logs"`, just create logs folder beforehand), replace the one in server folder, and reload viewer page.
