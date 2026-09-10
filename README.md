# CodinGame Summer Challenge 2026 BackTrackKing CLI runner

This is a referee for CodinGame's Summer Challenge 2026 with command line interface adapted for usage with [cg-brutaltester](https://github.com/dreignier/cg-brutaltester)

https://www.codingame.com/contests/summer-challenge-2026-back-track-king

## Build

- Install Java 17 and Maven
- Run `mvn package` in the root dir where pom.xml file is

The compiled jar file is in ./target/summer-challenge-2026-back-track-king-1.0-SNAPSHOT.jar

## Run

Get cg-brutaltester from Releases or by building as described in its readme-file ([cg-brutaltester](https://github.com/dreignier/cg-brutaltester))

You can copy both referee and cg-brutaltester JAR files, i.e. summer-challenge-2026-back-track-king-1.0-SNAPSHOT.jar and cg-brutaltester-1.0.0.jar, to the same directory to make handling paths easier.

This is a sample command that works, you can change options as described in the BrutalTester readme-file.

```
java -jar cg-brutaltester-1.0.0.jar -r "java -jar .\target\summer-challenge-2026-back-track-king-1.0-SNAPSHOT.jar" -p1 ".\YourBot.exe" -p2 "python `.\config\level2\Boss.py" -t 1 -n 5
```

It might be a bug, but it might work only after 2nd time running the command (might need running web-server).

Use `-Dleague.level=3` to run Bronze league logic - without tutorial objectives.
```
java -jar cg-brutaltester-1.0.0.jar -r "java -Dleague.level=3 -jar .\target\summer-challenge-2026-back-track-king-1.0-SNAPSHOT.jar" -p1 ".\YourBot.exe" -p2 "python `.\config\level2\Boss.py" -t 1 -n 5
```

## Inspect games

After running games you will see `http://localhost:8888/test.html` in the console.
This is a local web server where you can inspect the games. Next lines shows where it is located on your system.

For some reason asset paths are broken and the viewer just shows black rectangle, so a temporary fix is to just copy everything that's in /assets folder, create one more /assets folder inside it and paste everything there.

It might be a bug, but you might need to stop the server manually when you don't need it anymore.
