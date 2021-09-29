# StyleGAN2_experiment
GAN을 이용한 재난영상 생성 결과 정리


# GAN을 이용한 재난영상 생성
----------------
## [DCGAN](https://arxiv.org/pdf/1511.06434.pdf)을 사용한 재난 영상 생성
 
#### Classification에서 사용하는 Augmentation을 적용한 결과 Augmentation이 적용된 영상이 생성됨
#### 또한 Augmentation을 적용하지 않았을 경우 모드붕괴(Mode Collapse) 현상이 발견됨
###### 해상도 : (128x128)
| Augmentation X | Augmentation(flip, transfer, rotate) | 
| ------- | :------ |
| ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/DCGAN%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%A6%9D%EA%B0%95%20X%EA%B2%B0%EA%B3%BC%20128x128.png) | ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/DCGAN%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%A6%9D%EA%B0%95_filp_transfer_rotate%20%EA%B2%B0%EA%B3%BC%20128x128.png) |


#### GAN에서 사용되는 Augmentation 기법 적용 ([Differentiable Augmentation for Data-Efficient GAN Training](https://arxiv.org/pdf/2006.10738.pdf))
##### 실제 영상 VS DCGAN 생성 영상 ( 건물 화재 )
###### 해상도 : (256x256)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/DCGAN%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%A6%9D%EA%B0%95%20X%EA%B2%B0%EA%B3%BC%20128x128.png)

##### 실제 영상 VS DCGAN 생성 영상 ( 산불 )
###### 해상도 : (256x256)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/DCGAN%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%A6%9D%EA%B0%95%20X%EA%B2%B0%EA%B3%BC%20128x128.png)


----------------
## [StyleGAN2](https://arxiv.org/pdf/1511.06434.pdf)을 사용한 재난 영상 생성
#### 실제 영상 VS StyleGAN2 생성 영상
###### 해상도 : (256x256),(128x128),(64x64)
| Real Image | StyleGAN2 image | 
| ------- | :------ |
| ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/DCGAN%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%A6%9D%EA%B0%95%20X%EA%B2%B0%EA%B3%BC%20128x128.png) | ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/DCGAN%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%A6%9D%EA%B0%95_filp_transfer_rotate%20%EA%B2%B0%EA%B3%BC%20128x128.png) |