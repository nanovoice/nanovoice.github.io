# NanoVoice: Efficient Speaker-Adaptive Text-to-Speech for Multiple Speakers (ICASSP 2025, Oral Presentation)

#### This page and the demos below are intended solely for research demonstration.

### Authors
- Nohil Park <a href="pnoil2588@snu.ac.kr">pnoil2588@snu.ac.kr</a>
- Heeseung Kim <a href="gmltmd789@snu.ac.kr">gmltmd789@snu.ac.kr</a>
- Che Hyun Lee <a href="saga1214@snu.ac.kr">saga1214@snu.ac.kr</a>
- Jooyoung Choi <a href="jy_choi@snu.ac.kr">jy_choi@snu.ac.kr</a>
- Jiheum Yeom <a href="quilava1234@snu.ac.kr">quilava1234@snu.ac.kr</a>
- Sungroh Yoon (Corresponding author) <a href="sryoon@snu.ac.kr">sryoon@snu.ac.kr</a>

## Abstract
We present NanoVoice, a personalized text-to-speech model that efficiently constructs voice adapters for multiple speakers simultaneously. NanoVoice introduces a batch-wise speaker adaptation technique capable of fine-tuning multiple references in parallel, significantly reducing training time. Beyond building separate adapters for each speaker, we also propose a parameter sharing technique that reduces the number of parameters used for speaker adaptation. By incorporating a novel trainable scale matrix, NanoVoice mitigates potential performance degradation during parameter sharing. NanoVoice achieves performance comparable to the baselines, while training 4 times faster and using 45 percent fewer parameters for speaker adaptation with 40 reference voices. Extensive ablation studies and analysis further validate the efficiency of our model.

## LibriSpeech Dataset
**For the model comparison with the baseline, all samples were resampled to 16kHz and normalized to -27dB to ensure fairness. For the remaining experiments, as they were based on our model, all samples were kept at the original sampling rate of 22kHz.**

### Model Comparison

Transcript: Why fades the lotus of the water?

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">GT</th>
			<th style="text-align: center">NanoVoice</th>
			<th style="text-align: center">VoiceTailor</th>
			<th style="text-align: center">UnitSpeech</th>
			<th style="text-align: center">XTTS $v2$</th>
			<th style="text-align: center">CosyVoice</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/1_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/1_gt.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/1_nanovoice.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/1_voicetailor.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/1_unitspeech.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/1_xtts.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/1_cosyvoice.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

Transcript: For, like as not, they must have thought him a prince when they saw his fine cap.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">GT</th>
			<th style="text-align: center">NanoVoice</th>
			<th style="text-align: center">VoiceTailor</th>
			<th style="text-align: center">UnitSpeech</th>
			<th style="text-align: center">XTTS $v2$</th>
			<th style="text-align: center">CosyVoice</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/2_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/2_gt.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/2_nanovoice.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/2_voicetailor.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/2_unitspeech.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/2_xtts.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/2_cosyvoice.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

Transcript: But the general distinction is not on that account to be overlooked.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">GT</th>
			<th style="text-align: center">NanoVoice</th>
			<th style="text-align: center">VoiceTailor</th>
			<th style="text-align: center">UnitSpeech</th>
			<th style="text-align: center">XTTS $v2$</th>
			<th style="text-align: center">CosyVoice</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/3_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/3_gt.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/3_nanovoice.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/3_voicetailor.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/3_unitspeech.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/3_xtts.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/model_comparison/3_cosyvoice.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

### Ablation Studies

#### Adapter Sharing

Transcript: What is your country Olaf? Have you always been a Thrall? The Thrall's eyes flashed.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">Share None</th>
			<th style="text-align: center">Share $B$ <strong>(default)</strong></th>
			<th style="text-align: center">Share $A$</th>
			<th style="text-align: center">Share $B$, $A$</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/1_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/1_batch-wise.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/1_shareB.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/1_shareA.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/1_shareBA.flac" type="audio/flac"></audio></td>			
		</tr>
	</tbody>
</table>

Transcript: Nine thousand years have elapsed since she founded yours, and eight thousand since she founded ours as our annals record.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">Share None</th>
			<th style="text-align: center">Share $B$ <strong>(default)</strong></th>
			<th style="text-align: center">Share $A$</th>
			<th style="text-align: center">Share $B$, $A$</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/2_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/2_batch-wise.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/2_shareB.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/2_shareA.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/2_shareBA.flac" type="audio/flac"></audio></td>			
		</tr>
	</tbody>
</table>

Transcript: Federal judges and United States attorneys in Utah, who were not Mormons nor lovers of Mormonism, refused to entertain complaints, or prosecute cases under the law because of its manifest injustice and inadequacy.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">Share None</th>
			<th style="text-align: center">Share $B$ <strong>(default)</strong></th>
			<th style="text-align: center">Share $A$</th>
			<th style="text-align: center">Share $B$, $A$</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/3_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/3_batch-wise.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/3_shareB.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/3_shareA.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_share/3_shareBA.flac" type="audio/flac"></audio></td>			
		</tr>
	</tbody>
</table>

#### Trainable Scale Matrix

- NanoVoice
- w/o Normalization: Shared matrix $B$ with batched $A'$ multiplied by scale matrix $m'$ without normalizing with $\Vert W_0+\alpha\cdot BA'\Vert_c$.
- w/o Scale Matrix: Shared matrix $B$ with batched $A'$

Transcript: a feeling of freedom and I was awake. Where?

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center"><strong>NanoVoice (default)</strong></th>
			<th style="text-align: center">w/o Normalization</th>
			<th style="text-align: center">w/o Scale Matrix</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/1_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/1_nanovoice.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/1_no_normalization.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/1_no_scale.flac" type="audio/flac"></audio></td>			
		</tr>
	</tbody>
</table>

Transcript: What is your country Olaf? Have you always been a Thrall? The Thrall's eyes flashed.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center"><strong>NanoVoice (default)</strong></th>
			<th style="text-align: center">w/o Normalization</th>
			<th style="text-align: center">w/o Scale Matrix</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/2_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/2_nanovoice.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/2_no_normalization.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/2_no_scale.flac" type="audio/flac"></audio></td>			
		</tr>
	</tbody>
</table>

Transcript: What you had best do, my child, is to keep it and pray to it that since it was a witness to your undoing, it will deign to vindicate your cause by its righteous judgment.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center"><strong>NanoVoice (default)</strong></th>
			<th style="text-align: center">w/o Normalization</th>
			<th style="text-align: center">w/o Scale Matrix</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/3_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/3_nanovoice.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/3_no_normalization.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/ablation_scale/3_no_scale.flac" type="audio/flac"></audio></td>			
		</tr>
	</tbody>
</table>

### Analysis

#### Number of Speakers

Transcript: John Wesley Combash, Jacob Taylor, and Thomas Edward Skinner.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">Batch Size = 1</th>
			<th style="text-align: center">Batch Size = 5</th>
			<th style="text-align: center">Batch Size = 20</th>
			<th style="text-align: center">Batch Size = 40</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_batch_size/1_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_batch_size/1_bs1.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_batch_size/1_bs5.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_batch_size/1_bs20.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_batch_size/1_bs40.flac" type="audio/flac"></audio></td>			
		</tr>
	</tbody>
</table>

Transcript: Not all the Galatians had become perverted.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">Batch Size = 1</th>
			<th style="text-align: center">Batch Size = 5</th>
			<th style="text-align: center">Batch Size = 20</th>
			<th style="text-align: center">Batch Size = 40</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_batch_size/2_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_batch_size/2_bs1.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_batch_size/2_bs5.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_batch_size/2_bs20.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_batch_size/2_bs40.flac" type="audio/flac"></audio></td>			
		</tr>
	</tbody>
</table>

#### Role of Shared Matrix $B$

Transcript: The strong position held by the Edison system under the strenuous competition that was already springing up was enormously improved by the introduction of the three wire system and it gave an immediate impetus to incandescent lighting.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">Mixed-Gender</th>
			<th style="text-align: center">Same-Gender</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_gender/1_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_gender/1_mix.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_gender/1_same.flac" type="audio/flac"></audio></td>
		</tr>
	</tbody>
</table>

Transcript: There is the slang of the affected lady as well as of the PRECIEUSES.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">Mixed-Gender</th>
			<th style="text-align: center">Same-Gender</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_gender/2_ref.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_gender/2_mix.flac" type="audio/flac"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wav/analysis_gender/2_same.flac" type="audio/flac"></audio></td>
		</tr>
	</tbody>
</table>

