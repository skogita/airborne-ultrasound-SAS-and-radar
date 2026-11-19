# Mobile SAS — simulator and processing apps for airborne-ultrasound approach sensing — companion apps and source for the book

Companion apps and source for the book ***Toward a Million Lines XXX — Mobile SAS: Measuring Approach with Ultrasound*** (Japanese title 『LLM で 100 万行のソフトウェア開発 XXX — モバイル SAS — 超音波で接近を測る』; the book is in Japanese; the volume title is provisional).

The book studies, **by simulation only (no real device was built)**, how an airborne-ultrasound synthetic-aperture sonar (SAS) and a radar-style (FMCW and array) processing, mounted on a **drone** (20-40 kHz) or a **vehicle** (35-45 kHz), can measure the **distance and the change of distance** of an approaching wall, person, post, curb or tree. The engine (`sasmob`, Python) simulates per-element, per-chirp raw beat signals from a settings file (JSON) and processes them (range compression, range-velocity, azimuth-elevation beamforming, MVDR, time-domain back-projection). Two **separate** Windows apps (Flutter) sit on top of it: a **simulator app** and a **processing app**. The apps contain no computation; every button starts an engine command, and the same commands can be typed without the windows.

## Download

**Ready-to-run apps are on the [Releases](../../releases) page**, not in this repository. The release has two ZIPs:

| File | Contents |
|:---|:---|
| `sasmob_exe.zip` | The two Windows apps, ready built (**Japanese screens**), in separate folders (`processor\` and `simulator\`), with the engine source (`tools_for_run\`), `requirements.txt`, sample settings and the license files |
| `sasmob_exe_en.zip` | The same two apps (**English screens**) |

The apps need Python 3.11 or later on your PC (see the README inside the ZIPs; run `pip install -r requirements.txt`). The apps are **not code-signed**, so Windows may warn you. There is no APK. Data and processing results are not included; the simulator makes the raw data. **Creating raw data takes 1 to 8 minutes** depending on the machine. The design documents and the full source tree are not published in this release.

You are free to change the code and compare the results.

---

## License

- **The author holds the copyright.**
- **The code is under the GNU General Public License v3.0 or later (GPL-3.0-or-later).** The full text is [`LICENSE`](LICENSE). **If you modify it and distribute it, you must publish the source under the same GPL-3.0-or-later terms.**
- **The text (the READMEs and the other written text of this repository, and the text of the matching book) is under the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0).** See [`LICENSE-DOCS.md`](LICENSE-DOCS.md).
- **If you use them, say so.** State where it came from (the title of the book and the name of this repository) and keep the copyright notice. If you changed it, say that you changed it.
- Third-party components (numpy, scipy, matplotlib and psutil installed by `pip install -r requirements.txt`; the Flutter engine inside the EXEs) remain under their own original licenses.
- The rights to the public air-SAS dataset that the book reproduces (Blanford et al., "An in-air synthetic aperture sonar dataset of target scattering in environments of varying complexity," Scientific Data 11, 1196, 2024, doi:10.1038/s41597-024-04050-0) stay with the provider. The data are not in this repository, and the apps do not use them (the apps handle simulated raw data only).
- Provided "as is", without warranty — as the GPL-3.0 text says.

## 著作権とライセンス

- **著作権は、著者にあります。**
- **コードは、GNU General Public License v3.0 以降（GPL-3.0-or-later）です。**全文は [`LICENSE`](LICENSE) です。**改変して配布するときは、同じ GPL-3.0 以降の条件で、ソースを公開する義務があります。**
- **文章（このリポジトリの README ほかの文章と、対応する本の文章）は、Creative Commons 表示-継承 4.0 国際（CC BY-SA 4.0）です。**内容は [`LICENSE-DOCS.md`](LICENSE-DOCS.md) です。
- **使ったときは、使ったことを書いてください。**どこから使ったか（本の題名と、このリポジトリの名前）と、著作権の表示を、使った先に書いてください。直したときは、直したことも書いてください。
- 第三者の部品（`pip install -r requirements.txt` で入る numpy・scipy・matplotlib・psutil、EXE の中の Flutter の engine）は、それぞれの元のライセンスのままです。
- 本が再現している、空気中の SAS の公開データ（Blanford ほか「An in-air synthetic aperture sonar dataset of target scattering in environments of varying complexity」Scientific Data 11, 1196, 2024, doi:10.1038/s41597-024-04050-0）の権利は、提供元に残ります。データはこのリポジトリに含みません。アプリも使いません（アプリが扱うのは、シミュレーションの生データだけです）。
- 現状のまま（as is）提供します。保証はありません（GPL-3.0 の全文のとおりです）。
