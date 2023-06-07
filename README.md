# Powerset multi-class cross entropy loss for neural speaker diarization

[Alexis Plaquet](https://frenchkrab.github.io/) and [Hervé Bredin](https://herve.niderb.fr)  
Proc. InterSpeech 2023.

> Since its introduction in 2019, the whole end-to-end neural diarization (EEND) line of work has been addressing speaker diarization as a frame-wise multi-label classification problem with permutation-invariant training. Despite EEND showing great promise, a few recent works took a step back and studied the possible combination of (local) supervised EEND diarization with (global) unsupervised clustering. Yet, these hybrid contributions did not question the original multi-label formulation. We propose to switch from multi-label (where any two speakers can be active at the same time) to powerset multi-class classification (where dedicated classes are assigned to pairs of overlapping speakers). Through extensive experiments on 9 different benchmarks, we show that this formulation leads to significantly better performance (mostly on overlapping speech) and robustness to domain mismatch, while eliminating the detection threshold hyperparameter, critical for the multi-label formulation.

## Citations

```bibtex
@inproceedings{Plaquet2023,
  title={Powerset multi-class cross entropy loss for neural speaker diarization},
  author={Plaquet, Alexis and Bredin, Herv\'{e}},
  year={2023},
  booktitle={Proc. Interspeech 2023},
}

@inproceedings{Bredin2023,
  title={pyannote.audio 2.1 speaker diarization pipeline: principle, benchmark, and recipe},
  author={Bredin, Herv\'{e}},
  year={2023},
  booktitle={Proc. Interspeech 2023},
}
```

## Benchmark (and checkpoints)


### Pretrained model

Performance obtained with a model pretrained on AISHELL, AliMeeting, AMI, Ego4D, MSDWild, REPERE, and VoxConverse (see the paper for more details).

The [pretrained model checkpoint](models/powerset/powerset_pretrained.ckpt) used to obtain these results is available.


|Dataset | [DER%](. "Diarization error rate") | [FA%](. "False alarm rate") | [Miss%](. "Missed detection rate") | [Conf%](. "Speaker confusion rate") | Output | Metrics |
|---|---|---|---|---|---|---|
[AISHELL-4 (*channel 1*)](http://www.openslr.org/111/) | 16.85 | 3.25 | 6.29 | 7.30 | [:clipboard:](rttm/powerset/pretrained/AISHELL.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/AISHELL.SpeakerDiarization.Benchmark.test.eval)
[AliMeeting (*channel 1*)](https://www.openslr.org/119/) | 23.30 | 3.69 | 10.38 | 9.22 | [:clipboard:](rttm/powerset/pretrained/AliMeeting.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/AliMeeting.SpeakerDiarization.Benchmark.test.eval)
[AMI (*headset mix*)](https://groups.inf.ed.ac.uk/ami/corpus/) | 19.71 | 4.51 | 8.54 | 6.66 | [:clipboard:](rttm/powerset/pretrained/AMI.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/AMI.SpeakerDiarization.Benchmark.test.eval)
[AMI (*array1, channel 1)*)](https://groups.inf.ed.ac.uk/ami/corpus/) | 21.96 | 5.06 | 9.65 | 7.26 | [:clipboard:](rttm/powerset/pretrained/AMI-SDM.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/AMI-SDM.SpeakerDiarization.Benchmark.test.eval)
[Ego4D *v1 (validation)*](https://arxiv.org/abs/2110.07058) | 57.25 | 6.33 | 30.75 | 20.16 | [:clipboard:](rttm/powerset/pretrained/Ego4D.SpeakerDiarization.Benchmark.development.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/Ego4D.SpeakerDiarization.Benchmark.development.eval)
[MSDWild]() | 29.17 | 6.64 | 8.80 | 13.73 | [:clipboard:](rttm/powerset/pretrained/MSDWILD.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/MSDWILD.SpeakerDiarization.Benchmark.test.eval)
[REPERE (*phase 2*)](https://islrn.org/resources/360-758-359-485-0/) | 8.35 | 2.10 | 2.36 | 3.89 | [:clipboard:](rttm/powerset/pretrained/REPERE.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/REPERE.SpeakerDiarization.Benchmark.test.eval)
[VoxConverse (*v0.3*)](https://github.com/joonson/voxconverse) | 11.56 | 4.74 | 2.68 | 4.14 | [:clipboard:](rttm/powerset/pretrained/VoxConverse.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/VoxConverse.SpeakerDiarization.Benchmark.test.eval)
[DIHARD-3 (*Full*)](https://arxiv.org/abs/2012.01477) | 29.90 | 14.40 | 7.18 | 8.33 | [:clipboard:](rttm/powerset/pretrained/DIHARD.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/DIHARD.SpeakerDiarization.Benchmark.test.eval)
| | | | | | | |
[This American Life](https://arxiv.org/abs/2005.08072) | 21.83 | 2.25 | 12.85 | 6.74 | [:clipboard:](rttm/powerset/pretrained/ThisAmericanLife.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/ThisAmericanLife.SpeakerDiarization.Benchmark.test.eval)
[AVA-AVD](https://arxiv.org/abs/2111.14448) | 60.60 | 18.54 | 16.19 | 25.87 | [:clipboard:](rttm/powerset/pretrained/AVA-AVD.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/pretrained/AVA-AVD.SpeakerDiarization.Benchmark.test.eval)

### Finetuned models

Performance obtained after training the pretrained model further on one domain.

|Dataset | [DER%](. "Diarization error rate") | [FA%](. "False alarm rate") | [Miss%](. "Missed detection rate") | [Conf%](. "Speaker confusion rate") | Output | Metrics | Checkpoint |
|---|---|---|---|---|---|---|---|
[AISHELL-4 (*channel 1*)](http://www.openslr.org/111/) | 13.21 | 4.42 | 3.29 | 5.50 | [:clipboard:](rttm/powerset/adapted/AISHELL.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/adapted/AISHELL.SpeakerDiarization.Benchmark.test.eval) | [:floppy_disk:](models/powerset/adapted/AISHELL.ckpt)
[AliMeeting (*channel 1*)](https://www.openslr.org/119/) | 24.49 | 4.62 | 8.80 | 11.07 | [:clipboard:](rttm/powerset/adapted/AliMeeting.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/adapted/AliMeeting.SpeakerDiarization.Benchmark.test.eval) | [:floppy_disk:](models/powerset/adapted/AliMeeting.ckpt)
[AMI (*headset mix*)](https://groups.inf.ed.ac.uk/ami/corpus/) | 17.98 | 4.34 | 8.21 | 5.43 | [:clipboard:](rttm/powerset/adapted/AMI.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/adapted/AMI.SpeakerDiarization.Benchmark.test.eval) | [:floppy_disk:](models/powerset/adapted/AMI.ckpt)
[AMI (*array1, channel 1)*)](https://groups.inf.ed.ac.uk/ami/corpus/) | 22.90 | 4.81 | 9.76 | 8.33 | [:clipboard:](rttm/powerset/adapted/AMI-SDM.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/adapted/AMI-SDM.SpeakerDiarization.Benchmark.test.eval) | [:floppy_disk:](models/powerset/adapted/AMI-SDM.ckpt)
[Ego4D *v1 (validation)*](https://arxiv.org/abs/2110.07058) | 48.16 | 8.88 | 21.35 | 17.93 | [:clipboard:](rttm/powerset/adapted/Ego4D.SpeakerDiarization.Benchmark.development.rttm) | [:chart_with_upwards_trend:](eval/powerset/adapted/Ego4D.SpeakerDiarization.Benchmark.development.eval) | [:floppy_disk:](models/powerset/adapted/Ego4D.ckpt)
[MSDWild]() | 28.51 | 6.10 | 8.07 | 14.34 | [:clipboard:](rttm/powerset/adapted/MSDWILD.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/adapted/MSDWILD.SpeakerDiarization.Benchmark.test.eval) | [:floppy_disk:](models/powerset/adapted/MSDWILD.ckpt)
[REPERE (*phase 2*)](https://islrn.org/resources/360-758-359-485-0/) | 8.16 | 1.92 | 2.64 | 3.60 | [:clipboard:](rttm/powerset/adapted/REPERE.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/adapted/REPERE.SpeakerDiarization.Benchmark.test.eval) | [:floppy_disk:](models/powerset/adapted/REPERE.ckpt)
[VoxConverse (*v0.3*)](https://github.com/joonson/voxconverse) | 10.35 | 3.86 | 2.77 | 3.72 | [:clipboard:](rttm/powerset/adapted/VoxConverse.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/adapted/VoxConverse.SpeakerDiarization.Benchmark.test.eval) | [:floppy_disk:](models/powerset/adapted/VoxConverse.ckpt)
[DIHARD-3 (*Full*)](https://arxiv.org/abs/2012.01477) | 21.31 | 4.77 | 8.72 | 7.82 | [:clipboard:](rttm/powerset/adapted/DIHARD.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/adapted/DIHARD.SpeakerDiarization.Benchmark.test.eval) | [:floppy_disk:](models/powerset/adapted/DIHARD.ckpt)
| | | | | | | |
[AVA-AVD](https://arxiv.org/abs/2111.14448) | 46.45 | 6.71 | 17.75 | 21.98 | [:clipboard:](rttm/powerset/adapted/AVA-AVD.SpeakerDiarization.Benchmark.test.rttm) | [:chart_with_upwards_trend:](eval/powerset/adapted/AVA-AVD.SpeakerDiarization.Benchmark.test.eval) | [:floppy_disk:](models/powerset/adapted/AVA-AVD.ckpt)


## Reproducibility

### Reproducing the paper results
The [pyannote.audio](https://github.com/pyannote/pyannote-audio) version used to train these model is commit [e3dc7d6](https://github.com/pyannote/pyannote-audio/commit/e3dc7d68cc60c7d4f89df005b58674aa936b0882) (although it should not matter for this training, to be more precise it's commit [1f83e0b](https://github.com/pyannote/pyannote-audio/commit/1f83e0b867e5b9e0221e238e7955b7d6fc4ea967) with commit [e3dc7d6](https://github.com/pyannote/pyannote-audio/commit/e3dc7d68cc60c7d4f89df005b58674aa936b0882) changes cherry-picked).

More recent versions should also work. You only need to clone/download and install pyannote.audio as well as its dependencies. See pyannote.audio's README for more details.

### Example notebook : Adapting a powerset model and looking at its outputs

[In this notebook available on Google Colab](https://colab.research.google.com/drive/1S7ayat76N-xluD4gvN958O7QCpW8-u0l?usp=sharing), you can see how to load a powerset model (for example, one available in [models/]()), how to train it further on a toy dataset, and finally how to get its local segmentation output and final diarization output.

### Using checkpoints in a pipeline
```python
from pyannote.audio.models.segmentation import PyanNet
from pyannote.audio.pipelines import SpeakerDiarization as SpeakerDiarizationPipeline

# constants (params from the pyannote/speaker-diarization huggingface pipeline)
WAV_FILE="../pyannote-audio/tutorials/assets/sample.wav"
MODEL_PATH="models/powerset/powerset_pretrained.ckpt"
PIPELINE_PARAMS = {
    "clustering": {
        "method": "centroid",
        "min_cluster_size": 15,
        "threshold": 0.7153814381597874,
    },
    "segmentation": {
        "min_duration_off": 0.5817029604921046,
        # "threshold": 0.4442333667381752,  # does not apply to powerset
    },
}

# create, instantiate and apply the pipeline
pipeline = SpeakerDiarizationPipeline(
    segmentation=MODEL_PATH,
    embedding="speechbrain/spkrec-ecapa-voxceleb",
    embedding_exclude_overlap=True,
    clustering="AgglomerativeClustering",
)
pipeline.instantiate(PIPELINE_PARAMS)
pipeline(WAV_FILE)
```

### Using checkpoints for the segmentation model only
```python
from pyannote.audio import Model
from pyannote.audio.tasks import SpeakerDiarization
from pyannote.audio.core.inference import Inference

MODEL_PATH="models/powerset/powerset_pretrained.ckpt"
WAV_FILE="../pyannote-audio/tutorials/assets/sample.wav"

model : SpeakerDiarization = Model.from_pretrained(MODEL_PATH)
inference = Inference(model, step=5.0)
inference(WAV_FILE)
```

### Training your own powerset segmentation model
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

