# performance compare:

## tables
### comparison of different method of orb feature detection
| 500 keypoints detect | OpencvOrb | EmscriptenOrb |    jsfeat    |    AsmjsOrb  |   ShaderOrb  | Asmjs_ShaderOrb |
|:--------------------:|:---------:|:-------------:|:------------:|:------------:|:------------:|:---------------:|
|     library size     |     -     |     416KB     |    64.5KB    |    11.9KB    |    52.8KB    |     87.1KB      |
|     picture size     |  500*375  |    500*375    |    500*375   |   500*375    |    500*375   |     500*375     |
|   num of keypoints   |    500    |      500      |      500     |     500      |      500     |       500       |
|  chrome runtime(*20) |     -     |    62770ms    |    3552ms    |    1188ms    |    4930ms    |     63737ms     |
| firefox runtime(*20) |     -     |     8021ms    |   36580ms    |    2456ms    |   59573ms    | more than 2 mins|
|    c++ runtime(*20)  |  11680ms  |       -       |       -      |      -       |       -      |        -        |

### comparison by size of picture(best runtime)(500 keypoints)
| picture size | OpencvOrb | EmscriptenOrb |    jsfeat    |   AsmjsOrb   |   ShaderOrb  | Asmjs_ShaderOrb |
|:------------:|:---------:|:-------------:|:------------:|:------------:|:------------:|:---------------:|
|   500 * 375  |  11680ms  |     8021ms    |    3552ms    |    1188ms    |    4930ms    |     63737ms     |
|   600 * 800  |  18609ms  |    13901ms    |    6629ms    |    2525ms    |    5386ms    |     55103ms     |
|  750 * 1000  |  20233ms  |    19940ms    |    9547ms    |    2502ms    |    6787ms    |     62583ms     |
|  1200 * 800  |  22691ms  |    24022ms    |   11142ms    |    2684ms    |    5912ms    |     67230ms     |

### comparison by keypoints detected(best runtime)(picture 500*375)
| keypoints detect | OpencvOrb | EmscriptenOrb |    jsfeat    |   AsmjsOrb   |   ShaderOrb  | Asmjs_ShaderOrb |
|:----------------:|:---------:|:-------------:|:------------:|:------------:|:------------:|:---------------:|
|        100       |  11996ms  |     7840ms    |    3402ms    |     779ms    |    4920ms    |     91512ms     |
|        500       |  11680ms  |     8021ms    |    3552ms    |    1188ms    |    4930ms    |     63737ms     |
|       1000       |  12137ms  |     8325ms    |    4837ms    |    1745ms    |    4738ms    |     73355ms     |
|       5000       |  16136ms  |     8850ms    |    4324ms    |    2495ms    |    4801ms    |     33496ms     |
|     max(9644)    |  14118ms  |    10943ms    |    5147ms    |    2901ms    |    4778ms    |     49277ms     |

## graphs
### comparison of size of picture
![image](http://gitlab.patrick.quaidesapps.com/internal/ye-library/blob/master/ye_library/benchmark%20of%20all%20methods/graph1.jpg)

### comparison of keypoints detected
![image](http://gitlab.patrick.quaidesapps.com/internal/ye-library/blob/master/ye_library/benchmark%20of%20all%20methods/graph1.jpg)

## conclusion:
