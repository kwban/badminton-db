# badminton-db

A project to annotate badminton videos with data suited for tactical analysis. The current repo consists of TWO formats of annotated files, EAF and JSON.

##### Published paper

[BadmintonDB: A Badminton Dataset for Player-specific Match Analysis and Prediction](https://dl.acm.org/doi/abs/10.1145/3552437.3555696)

##### EAF

Using ELAN annotation tool, the annotated info (tier) are (to update on the table):

| **Tier**        | **Description**                                                                                                                                                                                                             |
| :-------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Points          | The score won by the players.                                                                                                                                                                                               |
| Strokes         | A hitting action performed by the player.                                                                                                                                                                                   |
| Visibility      | Tells if a point/ rally is completely visible. A point is considered visible if all strokes in the point, from Serve to Ending, are recognisable regardless of the Camera view.                                             |
| Errors          | Indicates the type of error in a video segment that causes the annotator to be unable to annotate.                                                                                                                          |
| Camera          | Describes the viewpoint of the camera that captures the match.                                                                                                                                                              |
| Service-Receive | Describes the location of players and the beginning server and receiver on the court. <br> Eg: T1P1S: T2P1R means Team 1 Player 1 serves at the top of the court while Team 2 Player 1 receives at the bottom of the court. |

#### JSON (to update)

A transformed format from EAF to fit our own needs, the info is being structured as follows:

```json
"VideoInfo": {
    "Camera": ,
    "Visibility": ,
    "Error": ,
    "StrokeError":
},
"PointInfo": {
    "PointBegin": ,
    "PointEnd": ,
    "WonEnd": {
        "AtBegin": ,
        "AtEnd": ,
        "Cause":
    },
    "T1P1": {
        "Status": ,
        "Score":,
        "Point": ,
        "Location":
    },
    "T2P1": {
        "Status": ,
        "Score":,
        "Point":,
        "Location":
    },
    "Rally": {

    }
}
```
