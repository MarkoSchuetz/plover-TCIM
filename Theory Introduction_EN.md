# Theoretical explanation

This steno input method uses Zhuyin as the main input element, and is combined with a dictionary to achieve the steno functionality.
** Since Microsoft Excel has problems in processing the ㄯ character, the encoding system is changed to Pinyin, but it does not affect the learning of the theory. **

## Zhuyin and splitting

Since there are 37 Zhuyin symbols in total, but general steno machines only have about 22 to 28 keys, the keys must be pressed simultaneously to fully express all Zhuyin symbols.

Each Chinese character can be divided into initial symbol and final symbol, and the two do not interfere with each other. Therefore, the initial symbols and final symbols can be discussed separately:

### Initial symbols

The input of initial symbols only requires four keys, namely ㄅ, ㄆ, ㄇ, ㄈ and the change
key: "變".

The input method is as follows:

| encoding                  | direct input   | together with "變" |
|:-------------------------:|:--------------:|:----------------------:|
| `B,P,M,F`（individually） | ㄅ、ㄆ、ㄇ、ㄈ | ㄉ、ㄊ、ㄋ、ㄌ         |
| `BM`                      | ㄍ             | ㄎ                     |
| `PF`                      | ㄏ             | ㄖ                     |
| `BP`                      | ㄐ、ㄗ         | ㄓ                     |
| `MF`                      | ㄑ、ㄘ         | ㄔ                     |
| `BPMF`                    | ㄒ、ㄙ         | ㄕ                     |

* Since ㄗ, ㄘ, ㄙ and ㄐ, ㄑ, ㄒ do not appear with common finals in Chinese, the two sets of initial symbols are overlaid on the same encodings.

According to the description above, a simplified diagram can be drawn as follows:

![Initials Graph.jpeg](https://github.com/Quisette/TC_steno/blob/master/Pictures/Initials%20Graph.jpeg?raw=true)

### Finals and segmentation

Since Chinese finals include many compound sounds (such as ㄞ, ㄟ, ㄠ, ㄡ, ㄢ, ㄤ, ㄣ, ㄥ,
etc.), by converting them into (monosyllabic) segments, they can be input with fewer keystrokes.  Therefore, two official symbols that are no longer common
in modern Chinese are introduced here:

| phonetic notation | pronunciation  | where to use       |
|-------------------|----------------|--------------------|
| ㄯ                | 即ㄢ、ㄣ之尾音 | ㄢ＝ㄚㄯ、ㄣ＝ㄜㄯ |
| ㆭ                | 即ㄤ、ㄥ之尾音 | ㄤ＝ㄚㆭ、ㄥ＝ㄜㆭ |

And define several "final segments"(TODO:check translation) and their encodings as follows:

| phonetic | encoding | remark                                           |
|----------|----------|--------------------------------------------------|
| ㄧ       | `I`      |                                                  |
| ㄨ       | `W`      |                                                  |
| ㄩ       | `IW`     | ㄧ、and tap ㄨ to type ㄩ                               |
| ㄚ       | `A`      |                                                  |
| ㄛ       | `AE`     | ㄚ、and tap ㄜ to type ㄛ                               |
| ㄜ       | `E`      |                                                  |
| ㄝ       | `E`      | the final 'ㄝ' is only used in '誒', so it shares the encoding with 'ㄜ'|
| ㄯ       | `N`      |                                                  |
| ㆭ       | `G`      |                                                  |
| ㄦ       | `NG`     | ㄯ、and tap ㆭ to type ㄦ                               |

All compound phonetic symbols are listed below:

| pronunciation | compound sound segments | encoding |
|---------------|-------------------------|----------|
| ㄞ            | ㄚㄧ                    | `IA`     |
| ㄟ            | ㄝㄧ                    | `IE`     |
| ㄠ            | ㄠㄨ                    | `WA`     |
| ㄡ            | ㄛㄨ                    | `WAE`    |
| ㄢ            | ㄚㄯ                    | `AN`     |
| ㄣ            | ㄜㄯ                    | `EN`     |
| ㄤ            | ㄚㆭ                    | `AG`     |
| ㄥ            | ㄜㆭ                    | `EG`     |

* "compound sound segments": refers to the way of expressing compound sounds
and finals with elemental finals


### Compound finals

The so-called compound finals refer to the finals composed of two  finals. Generally speaking, they can be combined by the above codes.

However, there are still some encoding conflicts in this system, which requires humans to
memorize the following rules:

* instead of 'ㄧㄞ', enter '`ㄧㄯ`'

* to input '一ㄚ', 'ㄧㄝ', 'ㄨㄚ', 'ㄨㄛ', 'ㄨㄞ', or 'ㄩㄝ' you must press the change
  key, "變", at the same time.

To sum up, a simple diagram illustrates this as follows:

![Finals Graph.jpeg](https://github.com/Quisette/TC_steno/blob/master/Pictures/Finals%20Graph.jpeg?raw=true)

## Encoding, keyboarding and input

The encodings are arranged in the following order on the keyboard：`ㄅㄆㄇㄈ變ㄧㄨㄚㄜㄯㆭ異`

在併擊時，系統會優先讀取前方的字元。 TODO: translate this...

When reading dictionary entries, you will see the following format: `Left code-right code/second group left code-second group right code/...`

The keyboard layout is as follows:

![Layout.jpeg](https://github.com/Quisette/TC_steno/blob/master/Pictures/Layout.jpeg?raw=true)

Note that the keyboard is symmetrical, so you need to type both sides. If you want to type
only one word, just type "變" on the right side. TODO: what's that key on a Gemini PR keyboard?

To delete the previous word, press the "變" key on both sides.

## Dictionary word selection

For word selection dictionary go to [Kaoffie's plover_next_stroke
Plugin](https://github.com/Kaoffie/plover_next_stroke) and install that plugin。

Turn on Next Stroke Suggestions as you type to use suggestion list.

## Number input

The number codes for this input method are arranged as follows: (press the special # key) 54321-67890. (Respectively corresponding to: `NAIMB-BMIAN`)

When it is necessary to enter numbers that are different from the order (in units of two
digits), the left Z key must be added.

Here's an example: Press #AN at the same time to enter the number 45; to enter 54, press #ANZ.







若有理論上之問題與建議，請在[Plover Discord社群](https://discord.com/invite/0lQde43a6dGmAMp2)的#multilingual討論區提出。

