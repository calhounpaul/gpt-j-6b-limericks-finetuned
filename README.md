Forked from Robert A. Gonsalves' [repo](https://github.com/robgon-art/DeepLimericks) related to the medium post ["I Once Trained an AI to Rhyme, and It Took GPT-J a Long Time. Since the Colab was slow, I upgraded to Pro. Each limerick cost me a dime."](https://towardsdatascience.com/i-once-trained-an-ai-to-rhyme-and-it-took-gpt-j-a-long-time-de1f98925e17)

More info can be found at [the huggingface.co repo for this project](https://huggingface.co/pcalhoun/gpt-j-6b-limericks-finetuned), where I'll maintain the latest bf16 weights as fine tuning progresses.

I've also added a gradio app so that anyone with sufficient GPU RAM to load the model for inference should also be able to share the interface over the web.

---

HF doesn't support 8bit training. As of this fork's forking (2/2/23) I've used deepspeed to finetune the bf16 weights to step 780 out of ~13000 (batch size 24). The weights on HF are still at step 540, but I'll push the latest revision today and give my pantry some time to cool off. Completing the bf16 training should take another two or three weeks.

Here's what the 8bit model (which completed FTing on the same dataset in ~36 hours with 1/3 the batch size) produces:

I've a limerick model file,<br>
Which, when opened, presents a pile<br>
Of bad-to-good verse.<br>
I don't think it's much worse<br>
Than the limerick I wrote in my style.<br>
<br>
On your index cards, write down your need,<br>
And arrange them in order of speed.<br>
When you're done, you'll recall<br>
Which one's quicker than all,<br>
And you'll know which is best, if indeed.
