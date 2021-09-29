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

# 추가실험
## StyleGAN2의 Mixing Regularization 응용

#### StyleGAN2 Architecture
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/stylegan2%20architecture.png)

###### -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### Mixing Regularization
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/StyleMixing%20%EC%84%A4%EB%AA%85.png)

###### 위 사진에서 보이는 바와 같이 Source A(이하 A), Source B(이하 B)가 있는 경우, 4x4부터 8x8 해상도에 해당하는 Layer 까지는 A로, 그 이후는 B로 학습하는 경우는 성별, 안경 착용 유무, 얼굴 각도 등이 B의 영향을 받는다. 하지만 16x16부터 32x32 해상도에 해당하는 Layer 부터 B로 학습할 경우 얼굴 각도, 안경 착용 유무, 성별 등은 A의 영향을 받고, 머리카락 색, 머리스타일 등은 B의 영향을 받는다. 즉 A의 영향력이 늘어났다. 마지막 64x64이상의 해상도에 해당하는 Layer 부터 B를 사용하여 학습한 경우는 배경색, 머리카락 색을 제외하고는 거의 다 A의 영향을 받는다. 이 방법을 응용하여 건물의 형태는 교회 데이터셋(약 1만개)으로 위의 사진에서는 Source A에 해당하고, 화재는 건물화재 데이터셋(약 500개)으로 위의 사진에서는 Source B에 해당하게 하여 해상도 16x16부터 32x32에 해당하는 Layer에서 두 Source를 교체하여 학습한다면 교회에 불이 붙은 영상이 생성될 것이다. 혹은 반대의 경우도 있다. 이 두 방법을 실험한 결과는 아래에 나와있다.

###### -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 교회 데이터셋을 사용한 Style Mixing
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EC%8A%A4%ED%83%80%EC%9D%BC%EB%AF%B9%EC%8B%B1%ED%85%8C%EC%8A%A4%ED%8A%B8.gif)

#### 방법1 (A:건물화재, B:교회)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EB%B0%A9%EB%B2%951.gif)

#### 방법2 (A:교회, B:건물화재)
![](https://github.com/Hwa-Jong/StyleGAN2_experiment/blob/main/imgs/%EB%B0%A9%EB%B2%952.gif)