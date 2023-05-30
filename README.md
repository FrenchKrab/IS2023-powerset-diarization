# Performance of speaker diarization using powerset segmentation models
## Out-of-the-box accuracy

Performance obtained with a model pretrained on AISHELL, AliMeeting, AMI, Ego4D, MSDWild, REPERE, and VoxConverse (see the paper for more details).

The [pretrained model checkpoint](models/powerset/powerset_pretrained.ckpt) used to obtain these results is available.

|Dataset | [DER%](. "Diarization error rate") | [FA%](. "False alarm rate") | [Miss%](. "Missed detection rate") | [Conf%](. "Speaker confusion rate") | Expected output | File-level evaluation |
|---|---|---|---|---|---|---|
[AISHELL-4 (*channel 1*)](http://www.openslr.org/111/) | 16.85 | 3.25 | 6.29 | 7.30 | [RTTM](rttm/powerset/pretrained/AISHELL.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/pretrained/AISHELL.SpeakerDiarization.Benchmark.test.eval)
[AliMeeting (*channel 1*)](https://www.openslr.org/119/) | 23.30 | 3.69 | 10.38 | 9.22 | [RTTM](rttm/powerset/pretrained/AliMeeting.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/pretrained/AliMeeting.SpeakerDiarization.Benchmark.test.eval)
[AMI (*headset mix*)](https://groups.inf.ed.ac.uk/ami/corpus/) | 19.71 | 4.51 | 8.54 | 6.66 | [RTTM](rttm/powerset/pretrained/AMI.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/pretrained/AMI.SpeakerDiarization.Benchmark.test.eval)
[AMI (*array1, channel 1)*)](https://groups.inf.ed.ac.uk/ami/corpus/) | 21.96 | 5.06 | 9.65 | 7.26 | [RTTM](rttm/powerset/pretrained/AMI-SDM.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/pretrained/AMI-SDM.SpeakerDiarization.Benchmark.test.eval)
[Ego4D *v1 (validation)*](https://arxiv.org/abs/2110.07058) | 57.25 | 6.33 | 30.75 | 20.16 | [RTTM](rttm/powerset/pretrained/Ego4D.SpeakerDiarization.Benchmark.development.rttm) | [eval](eval/powerset/pretrained/Ego4D.SpeakerDiarization.Benchmark.development.eval)
[MSDWild]() | 29.17 | 6.64 | 8.80 | 13.73 | [RTTM](rttm/powerset/pretrained/MSDWILD.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/pretrained/MSDWILD.SpeakerDiarization.Benchmark.test.eval)
[REPERE (*phase 2*)](https://islrn.org/resources/360-758-359-485-0/) | 8.35 | 2.10 | 2.36 | 3.89 | [RTTM](rttm/powerset/pretrained/REPERE.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/pretrained/REPERE.SpeakerDiarization.Benchmark.test.eval)
[VoxConverse (*v0.3*)](https://github.com/joonson/voxconverse) | 11.56 | 4.74 | 2.68 | 4.14 | [RTTM](rttm/powerset/pretrained/VoxConverse.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/pretrained/VoxConverse.SpeakerDiarization.Benchmark.test.eval)
[DIHARD-3 (*Full*)](https://arxiv.org/abs/2012.01477) | 29.90 | 14.40 | 7.18 | 8.33 | [RTTM](rttm/powerset/pretrained/DIHARD.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/pretrained/DIHARD.SpeakerDiarization.Benchmark.test.eval)
[This American Life](https://arxiv.org/abs/2005.08072) | 21.83 | 2.25 | 12.85 | 6.74 | [RTTM](rttm/powerset/pretrained/ThisAmericanLife.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/pretrained/ThisAmericanLife.SpeakerDiarization.Benchmark.test.eval)
[AVA-AVD](https://arxiv.org/abs/2111.14448) | 60.60 | 18.54 | 16.19 | 25.87 | [RTTM](rttm/powerset/pretrained/AVA-AVD.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/pretrained/AVA-AVD.SpeakerDiarization.Benchmark.test.eval)


## Accuracy after per-domain adaptation

Performance obtained after training the pretrained model further on one domain.

|Dataset | [DER%](. "Diarization error rate") | [FA%](. "False alarm rate") | [Miss%](. "Missed detection rate") | [Conf%](. "Speaker confusion rate") | Output | File-level evaluation | Model checkpoint |
|---|---|---|---|---|---|---|---|
[AISHELL-4 (*channel 1*)](http://www.openslr.org/111/) | 13.21 | 4.42 | 3.29 | 5.50 | [RTTM](rttm/powerset/adapted/AISHELL.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/adapted/AISHELL.SpeakerDiarization.Benchmark.test.eval) | [checkpoint](models/powerset/adapted/AISHELL.ckpt)
[AliMeeting (*channel 1*)](https://www.openslr.org/119/) | 24.49 | 4.62 | 8.80 | 11.07 | [RTTM](rttm/powerset/adapted/AliMeeting.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/adapted/AliMeeting.SpeakerDiarization.Benchmark.test.eval) | [checkpoint](models/powerset/adapted/AliMeeting.ckpt)
[AMI (*headset mix*)](https://groups.inf.ed.ac.uk/ami/corpus/) | 17.98 | 4.34 | 8.21 | 5.43 | [RTTM](rttm/powerset/adapted/AMI.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/adapted/AMI.SpeakerDiarization.Benchmark.test.eval) | [checkpoint](models/powerset/adapted/AMI.ckpt)
[AMI (*array1, channel 1)*)](https://groups.inf.ed.ac.uk/ami/corpus/) | 22.90 | 4.81 | 9.76 | 8.33 | [RTTM](rttm/powerset/adapted/AMI-SDM.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/adapted/AMI-SDM.SpeakerDiarization.Benchmark.test.eval) | [checkpoint](models/powerset/adapted/AMI-SDM.ckpt)
[Ego4D *v1 (validation)*](https://arxiv.org/abs/2110.07058) | 48.16 | 8.88 | 21.35 | 17.93 | [RTTM](rttm/powerset/adapted/Ego4D.SpeakerDiarization.Benchmark.development.rttm) | [eval](eval/powerset/adapted/Ego4D.SpeakerDiarization.Benchmark.development.eval) | [checkpoint](models/powerset/adapted/Ego4D.ckpt)
[MSDWild]() | 28.51 | 6.10 | 8.07 | 14.34 | [RTTM](rttm/powerset/adapted/MSDWILD.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/adapted/MSDWILD.SpeakerDiarization.Benchmark.test.eval) | [checkpoint](models/powerset/adapted/MSDWILD.ckpt)
[REPERE (*phase 2*)](https://islrn.org/resources/360-758-359-485-0/) | 8.16 | 1.92 | 2.64 | 3.60 | [RTTM](rttm/powerset/adapted/REPERE.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/adapted/REPERE.SpeakerDiarization.Benchmark.test.eval) | [checkpoint](models/powerset/adapted/REPERE.ckpt)
[VoxConverse (*v0.3*)](https://github.com/joonson/voxconverse) | 10.35 | 3.86 | 2.77 | 3.72 | [RTTM](rttm/powerset/adapted/VoxConverse.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/adapted/VoxConverse.SpeakerDiarization.Benchmark.test.eval) | [checkpoint](models/powerset/adapted/VoxConverse.ckpt)
[DIHARD-3 (*Full*)](https://arxiv.org/abs/2012.01477) | 21.31 | 4.77 | 8.72 | 7.82 | [RTTM](rttm/powerset/adapted/DIHARD.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/adapted/DIHARD.SpeakerDiarization.Benchmark.test.eval) | [checkpoint](models/powerset/adapted/DIHARD.ckpt)
[AVA-AVD](https://arxiv.org/abs/2111.14448) | 46.45 | 6.71 | 17.75 | 21.98 | [RTTM](rttm/powerset/adapted/AVA-AVD.SpeakerDiarization.Benchmark.test.rttm) | [eval](eval/powerset/adapted/AVA-AVD.SpeakerDiarization.Benchmark.test.eval) | [checkpoint](models/powerset/adapted/AVA-AVD.ckpt)



# Reproducability
## Using the checkpoints
**TODO**

## Reproducing the paper results
The [pyannote.audio](https://github.com/pyannote/pyannote-audio) version used to train these model is commit [e3dc7d6](https://github.com/pyannote/pyannote-audio/commit/e3dc7d68cc60c7d4f89df005b58674aa936b0882) (although it should not matter for this training, to be more precise it's commit [1f83e0b](https://github.com/pyannote/pyannote-audio/commit/1f83e0b867e5b9e0221e238e7955b7d6fc4ea967) with commit [e3dc7d6](https://github.com/pyannote/pyannote-audio/commit/e3dc7d68cc60c7d4f89df005b58674aa936b0882) changes cherry-picked).

## Training your own powerset segmentation model
You can train your own version of the model by using the [pyannote.audio](https://github.com/pyannote/pyannote-audio) develop branch (instructions in pyannote.audio's readme), or pyannote.audio v3.x when released.

The `SpeakerDiarization` task can be set to use powerset or multilabel representation with its `max_speakers_per_frame` constructor parameter : "*Maximum number of (overlapping) speakers per frame. Setting this value to 1 or more enables `powerset multi-class` training.*"

In this example, the model is ready to be trained with the powerset multiclass setting described in the paper, and will handle at most 4 speakers per 5-seconds chunk, and 2 active speakers simultaneously.

```python
from pyannote.database import registry
from pyannote.audio.tasks import SpeakerDiarization
from pyannote.audio.models.segmentation import PyanNet

my_protocol = registry.get_protocol('MyProtocol.SpeakerDiarization.Custom')

seg_task = SpeakerDiarization(
    my_protocol, 
    duration=5.0,
    max_speakers_per_chunk=4,
    max_speakers_per_frame=2,
)
model = PyanNet(task=seg_task)
```

# Citations 

**TODO**