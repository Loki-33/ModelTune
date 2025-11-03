# ModelTune

This is an attemot to teach a model simple mathematics like addition, subtraction etc...using techniques like Finetuning, RL-PPO tuning and their comparison. <br>

It was tested before that the model has no capabiliities whatsoever to even do simple mathematical task. It just generated random garbage text.

## OVERVIEW
Model Used: EleutherAI/pythia-410m <br>
1. **INSTRUCTION TUNE** (math-instruction-finetuning.ipynb)<br>
Trained on "tatsu-lab/alpaca" dataset, which contains a bunch on instructions. <br>
Trained using Lora-method, rank=8, alpha=16, target_modules=['query_key_value']<br>

2. **SFT-TUNED** (math-sft.ipynb)<br>
Then the instruction-tuned model, is futher tuned on my custom math dataset which contains a bunch of addition, subtraction, multiplication and BODMAS related questions. <br>
Again the training done on the lora-adapters. <br>
But to no avail the model still didnt learn to solve mathematical questions, but what it learned is to output atleast some numbers, whereas before it couldnt even do that.

4. **RL-TUNED** (math-rl-tuning.ipynb)<br>
The instruction tuned model, not sft trained, was trained on then RL-PPO method using the same math dataset. Again it just learned to output numbers not learn any pattern or logic in the calculation.<br>

I have to no compare whether RL or SFT method was better.<br>

As for now, my conclusion is that the model maybe too small to learn such patterns or maybe my methods were just bad.

### TODO
1. Further tune the sft-trained model with RL and another custom dataset.
