# 2022-ComputerVision-Project

## PyTorch-SuperGlue

본 프로젝트는 이미지 쌍의 Keypoints를 추출하여 Local Feature끼리 매칭을 시키는 Task이며, Computer Vision과 Ojbect Detection에서 중요한 Concept입니다. SuperGlue Network는 두 IMAGE SET의 Sparse Image Feature에 대해서 Correspondence를 수행하도록 훈련된 최적의 Matching layer와 결합된 GNN입니다.   
이 리포지토리에는 SuperPoint Keypoints 및 Description 위에 SuperGlue Matching Network를 실행하기 위한 PyTorch 코드 및 Pretrain-weights가 포함되어 있습니다. 
이미지 쌍이 주어지면 이 리포지토리를 사용하여 이미지 쌍에서 일치하는 Feature을 추출할 수 있습니다.

#### [Youtube](https://www.youtube.com/watch?v=QUXKib-jfEM)    |    [Eval_AI_git_Link](https://github.com/sejong-rcv/2022.Infra.EvalAI-Starters)    |    [Eval AI](http://203.250.148.128:3088/)    |    [Paper](https://arxiv.org/abs/1911.11763)


![123_1234_matches](https://user-images.githubusercontent.com/73326932/168055123-c43603cf-4015-4544-9fd8-d648dea203f4.png)

## DATASET
Download the COCO2014 dataset files for training

* **Training Dataset**
``` 
wget http://images.cocodataset.org/zips/train2014.zip
```
* **Validation Dataset**
```
wget http://images.cocodataset.org/zips/val2014.zip
```
* **Test Dataset**
```
wget http://images.cocodataset.org/zips/test2014.zip
```

## Dependencies
* Python 3
* PyTorch >= 1.1
* OpenCV >= 3.4 (4.1.2.30 recommended for best GUI keyboard interaction, see this note)
* Matplotlib >= 3.1
* NumPy >= 1.18

simple run : ```pip3 install numpy opencv-python torch matplotlib```

## Contents

### Training
```
python3 train.py
```

### Additional useful command line parameters
```--epoch``` : epoch의 수 (default : 20)    
```--train_path``` : training images 폴더의 path ex) /home/ubuntu/SuperGlue-pytorch/train2014/
```--eval_output_dir``` : output 폴더 경로 설정 (defalut : dump_match_pairs/)


### Visualization
![image](https://user-images.githubusercontent.com/73326932/168069210-85160549-535b-4c52-a7d4-046dc1a0aa96.png)



### Run Matching+Evaluation (match_pairs.py)
``` 
./match_pairs.py
```

### Get Result file({}_evaluation.npz in eval_output_di path)
```
./match_pairs.py --viz --eval --max_keypoints 1024
```



### 참고자료

* [SuperGluePretrainedNetwork](https://github.com/magicleap/SuperGluePretrainedNetwork)
* [SuperGlue PyTorch](https://github.com/HeatherJiaZG/SuperGlue-pytorch)
* [Feature Detection And Matching](https://medium.com/data-breach/introduction-to-feature-detection-and-matching-65e27179885d#:~:text=Features%20matching%20or%20generally%20image%20matching%2C%20a%20part,correspondences%20between%20two%20images%20of%20the%20same%20scene%2Fobject.)
* [SuperPoint](https://arxiv.org/abs/1712.07629)
