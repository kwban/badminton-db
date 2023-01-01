# badminton-db

A project to annotate badminton videos with data suited for tactical analysis. The current repo consists of TWO formats of annotated files, EAF and JSON.

##### Published paper

[BadmintonDB: A Badminton Dataset for Player-specific Match Analysis and Prediction](https://dl.acm.org/doi/abs/10.1145/3552437.3555696)

##### Videos (YouTube)

| **Match**                                                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------- |
| [2018-27-2R16-MS-Anthony Sinisuka GINTING (INA)-Kento MOMOTA (JPN)-BLIBLI Indonesia Open](https://www.youtube.com/watch?v=YKjJVB3d860)     |
| [2018-38-5F-MS-Anthony Sinisuka GINTING (INA)-Kento MOMOTA (JPN)-Victor China Open](https://www.youtube.com/watch?v=3mMzr0Rc94c)           |
| [2019-04-3QF-MS-Anthony Sinisuka GINTING (INA)-Kento MOMOTA (JPN)-Daihatsu Indonesia Masters](https://www.youtube.com/watch?v=KDRdcHx3dmI) |
| [2019-15-5F-MS-Anthony Sinisuka GINTING (INA)-Kento MOMOTA (JPN)-Singapore Open 2019](https://youtu.be/KkwNopIQkP4)                        |
| [2019-20-6SF-MS-Anthony Sinisuka GINTING (INA)-Kento MOMOTA (JPN)-Sudirman Cup](https://youtu.be/1kZwH8SU4BQ)                              |
| [2019-30-3QF-MS-Anthony Sinisuka GINTING (INA)-Kento MOMOTA (JPN)-Daihatsu Yonex Japan Open](https://youtu.be/YfyTSydRknQ)                 |
| [2019-38-5F-MS-Anthony Sinisuka GINTING (INA)-Kento MOMOTA (JPN)-Victor China Open](https://youtu.be/zPAuJIkpR3k)                          |
| [2019-43-3QF-MS-Anthony Sinisuka GINTING (INA)-Kento Momota (JPN)-YONEX French Open](https://www.youtube.com/watch?v=MkBe-khRTNs)          |
| [2019-50-5F-MS-Anthony Sinisuka GINTING (INA)-Kento MOMOTA (JPN)-HSBC BWF World Tour Finals](https://www.youtube.com/watch?v=-vBEdAfSX4w)  |

##### EAF

Using ELAN annotation tool, the annotated info (tier) are:

| **Tier**        | **Description**                                                                                                                                                                                                             |
| :-------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Points          | The score won by the players.                                                                                                                                                                                               |
| Strokes         | A hitting action performed by the player.                                                                                                                                                                                   |
| Visibility      | Tells if a point/ rally is completely visible. A point is considered visible if all strokes in the point, from Serve to Ending, are recognisable regardless of the Camera view.                                             |
| Errors          | Indicates the type of error in a video segment that causes the annotator to be unable to annotate.                                                                                                                          |
| Camera          | Describes the viewpoint of the camera that captures the match.                                                                                                                                                              |
| Service-Receive | Describes the location of players and the beginning server and receiver on the court. <br> Eg: T1P1S: T2P1R means Team 1 Player 1 serves at the top of the court while Team 2 Player 1 receives at the bottom of the court. |

For current 9 videos, T1 is refering to Ginting while T2 is refering to Momota.

#### JSON

A transformed format from EAF to fit our own needs, the info is being structured as follows:

```json
"VideoInfo": {
    "Visibility": ,
    "Error": ,
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
        "StrokeNum":,
        "Player":,
        "Camera":,
        "StrokeBegin":,
        "StrokeEnd":,
        "StrokeType": # key will be StrokeError if the value is error-tier
    }
}
```
