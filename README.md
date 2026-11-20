# Viaalink model mirror

Exact copies of third-party model files that Viaalink apps download. We host the bytes we tested, so a
re-upload upstream cannot change what our users run. Every file is pinned by SHA-256 in the app that
downloads it.

## Release `speaker-recognition-2026-09`

| File | SHA-256 | Source | Licence |
|---|---|---|---|
| 3dspeaker_speech_campplus_sv_en_voxceleb_16k.onnx | 357a834f702b80161e5b981182c038e18553c1f2ca752ed6cec2052365d4129b | k2-fsa/sherpa-onnx release `speaker-recongition-models`, as served before 2026-11-19 | Apache-2.0 (3D-Speaker CAM++, modelscope/3D-Speaker) |
| 3dspeaker_speech_campplus_sv_zh_en_16k-common_advanced.onnx | aa3cfc16963a10586a9393f5035d6d6b57e98d358b347f80c2a30bf4f00ceba2 | same | Apache-2.0 |

Why: on 2026-11-19 upstream re-uploaded these files, exported with a newer PyTorch. The weights are
unchanged, but 52 AveragePool nodes changed `count_include_pad` from 1 to 0, which changes the
voiceprints. Our thresholds were measured on the files above.

Apache-2.0: https://www.apache.org/licenses/LICENSE-2.0. The files are unmodified.
