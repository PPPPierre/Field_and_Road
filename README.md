<div align="center">
  <p>
    <img width="100%" src="https://github.com/PPPPierre/Field_and_Road/blob/main/imgs/train_1.png"></a>
  </p>
</div>

# <div align="center">Field_and_Road</div>

The classification task for Field and Road is not easy, because the features of scenario images are very complicated. The inter-class distance is small while the intra-class distance can be large.

We need a model that is strong enough to extract features from the dataset. However, the amount of images for training is limited. Therefore, finetuning is an appropriate way to finish this task.

These days, Transformer is very popular, but it's not device-friendly, especially for embedded systems. So I choose to use a ConvNet that has beaten Transformers in his time, which tells us that we still cannot ignore the potential of ConvNets. Its name is ConvNeXt, a fully convolutional network. Applied with many effective tricks and trained with cautious, it is a very good backbone for finetuning our task.

Paper: https://arxiv.org/abs/2201.03545

Source code: https://github.com/facebookresearch/ConvNeXt

The most of codes here are copied from the source code of ConvNeXt. I reorganized and rewrite some of them for making them concise and better break down their details.

## Implementation

The implementation is on the platform Colab and in using PyTorch. Please open the file **File_and_Road.ipynb** to check the whole report.

All details are included: source codes, trainning, results, and how to evaluate on your test data.

## Training

The model used is **ConvNeXt_base**, finetuned from the official weights on the Field_and_Road dataset. The finetuning used 30 epoches, more training details is shown in the notebook.

## Evaluation result

The test dataset is extended from 10 images to 20 images. I personally added 10 extra images. And the model acheived a **95% of TOP1-Acc**. It did a great job !

Visualization of the test results are shown below

<div align="center">
  <p>
    <img width="100%" src="https://github.com/PPPPierre/Field_and_Road/blob/main/imgs/test_result.png"></a>
  </p>
  <p>
    <img width="100%" src="https://github.com/PPPPierre/Field_and_Road/blob/main/imgs/test_result_2.png"></a>
  </p>
</div>

