# StyleGAN2_experiment
GAN을 이용한 재난영상 생성 결과 정리

----------------

# GAN을 이용한 재난영상 생성
## [DCGAN](https://arxiv.org/pdf/1511.06434.pdf)을 사용한 재난 영상 생성
 
#### Classification에서 사용하는 Augmentation을 적용한 결과 Augmentation이 적용된 영상이 생성됨
#### 또한 Augmentation을 적용하지 않았을 경우 모드붕괴(Mode Collapse) 현상이 발견됨
###### 해상도 : (128x128)
| Augmentation X | Augmentation(flip, transfer, rotate) | 
| ------- | :------ |
| ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/DCGAN%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%A6%9D%EA%B0%95%20X%EA%B2%B0%EA%B3%BC%20128x128.png) | ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/DCGAN%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%A6%9D%EA%B0%95_filp_transfer_rotate%20%EA%B2%B0%EA%B3%BC%20128x128.png) |

###### -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### GAN에서 사용되는 Augmentation 기법 적용 ([Differentiable Augmentation for Data-Efficient GAN Training](https://arxiv.org/pdf/2006.10738.pdf))
##### 실제 영상 VS DCGAN 생성 영상 ( 건물 화재 )
###### 해상도 : (256x256)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/DCGAN%20%EC%83%9D%EC%84%B1%20%EC%9D%B4%EB%AF%B8%EC%A7%80%20%EC%8B%A4%EC%A0%9C%20%EC%9D%B4%EB%AF%B8%EC%A7%80%EC%99%80%20%EB%B9%84%EA%B5%90%20256x256.png)

##### 실제 영상 VS DCGAN 생성 영상 ( 산불 )
###### 해상도 : (256x256)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/DCGAN%20%EC%83%9D%EC%84%B1%20%EC%9D%B4%EB%AF%B8%EC%A7%80%20%EC%8B%A4%EC%A0%9C%20%EC%9D%B4%EB%AF%B8%EC%A7%80%EC%99%80%20%EB%B9%84%EA%B5%90(%EC%82%B0%EB%B6%88)%20256x256.png)

###### -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### 실제 영상 VS DCGAN 생성 영상
###### 해상도 : (256x256),(128x128),(64x64)
| Real Image | DCGAN Image | 
| ------- | :------ |
| ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EC%8B%A4%EC%A0%9C%20%EC%9D%B4%EB%AF%B8%EC%A7%80%EC%99%80%20DCGAN%20%EC%9D%B4%EB%AF%B8%EC%A7%80%20%EB%B9%84%EA%B5%90_%EC%8B%A4%EC%A0%9C.png) | ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EC%8B%A4%EC%A0%9C%20%EC%9D%B4%EB%AF%B8%EC%A7%80%EC%99%80%20DCGAN%20%EC%9D%B4%EB%AF%B8%EC%A7%80%20%EB%B9%84%EA%B5%90.png) |

----------------
## [StyleGAN2](https://arxiv.org/pdf/1511.06434.pdf)를 사용한 재난 영상 생성
#### 실제 영상 VS StyleGAN2 생성 영상
###### 해상도 : (256x256),(128x128),(64x64)
| Real Image | StyleGAN2 Image | 
| ------- | :------ |
| ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EC%8B%A4%EC%A0%9C%20%EC%9D%B4%EB%AF%B8%EC%A7%80%EC%99%80%20DCGAN%20%EC%9D%B4%EB%AF%B8%EC%A7%80%20%EB%B9%84%EA%B5%90_%EC%8B%A4%EC%A0%9C.png) | ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EC%8B%A4%EC%A0%9C%20%EC%9D%B4%EB%AF%B8%EC%A7%80%EC%99%80%20stylegan2%20%EC%9D%B4%EB%AF%B8%EC%A7%80%20%EB%B9%84%EA%B5%90.png) |

#### DCGAN VS StyleGAN2 생성 영상
###### 해상도 : (256x256),(128x128),(64x64)
| DCGAN Image | StyleGAN2 Image | 
| ------- | :------ |
| ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EC%8B%A4%EC%A0%9C%20%EC%9D%B4%EB%AF%B8%EC%A7%80%EC%99%80%20DCGAN%20%EC%9D%B4%EB%AF%B8%EC%A7%80%20%EB%B9%84%EA%B5%90.png) | ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EC%8B%A4%EC%A0%9C%20%EC%9D%B4%EB%AF%B8%EC%A7%80%EC%99%80%20stylegan2%20%EC%9D%B4%EB%AF%B8%EC%A7%80%20%EB%B9%84%EA%B5%90.png) |

###### -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### 건물 데이터셋으로 사전학습 시키고 그 후 Fine-tuning
##### 기존 방법(건물화재 데이터셋만 이용)과 Fine-tuning 방법(건물 데이터셋으로 사전학습 후 건물화재 데이터셋으로 재학습)에 따른 비교
###### 해상도 : (512x512)
| 기존 방법 | Fine-tuning | 
| ------- | :------ |
| ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/fine-tuning%20%EC%A0%84%ED%9B%84%EB%B9%84%EA%B5%901.png) | ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/fine-tuning%20%EC%A0%84%ED%9B%84%EB%B9%84%EA%B5%902.png) |
| ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/fine-tuning%20%EC%A0%84%ED%9B%84%EB%B9%84%EA%B5%90-%EC%A7%80%EC%A7%841.png) | ![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/fine-tuning%20%EC%A0%84%ED%9B%84%EB%B9%84%EA%B5%90-%EC%A7%80%EC%A7%842.png) |


###### 기존 방법에서 표시된 부분을 보면 건물 형태가 이상한 것을 확인할 수 있다.
###### 하지만 사전학습 된 모델을 사용한 경우 이러한 문제가 어느정도 해결된 것을 확인할 수 있다.

###### -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## StyleGAN2 사용한 재난 영상 생성 최종 결과
###### 해상도 : (512x512)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EC%9E%AC%EB%82%9C%EC%98%81%EC%83%81%20%EC%B5%9C%EC%A2%85%20%EA%B2%B0%EA%B3%BC%20512x512.png)


#### 건물화재
###### 해상도 : (512x512)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EA%B1%B4%EB%AC%BC%ED%99%94%EC%9E%AC%20%EC%B5%9C%EC%A2%85%EA%B2%B0%EA%B3%BC%20best%20512x512.png)

#### 산불
###### 해상도 : (512x512)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EC%82%B0%EB%B6%88%20%EC%B5%9C%EC%A2%85%EA%B2%B0%EA%B3%BC%20best%20512x512.png)

#### 지진
###### 해상도 : (512x512)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EC%A7%80%EC%A7%84%20%EC%B5%9C%EC%A2%85%EA%B2%B0%EA%B3%BC%20best%20512x512.png)

#### 홍수
###### 해상도 : (512x512)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%ED%99%8D%EC%88%98%20%EC%B5%9C%EC%A2%85%EA%B2%B0%EA%B3%BC%20best%20512x512.png)


----------------