
- 장비에서 얻어지는 Pixel간의 distance가 있음. (pixel distance)
- 실제 영상의 좌표값의 취리와 데이터에서 보는 값과 차이가 있음.
	3차원의 경우 slice distance도 고려가 되어짐.

- Image를 같은 size로 맞추기 위해서 voxel spacing을 활용함.
- ![Screenshot from 2024-01-30 16-31-54](https://github.com/minyoungci/MedicalVideo/assets/80457917/25507f74-fbd7-46f4-bc8d-626c1fcfcb21)

#### Voxel Spacing

- 물리적인 위치라 실제 위치와 다름 
- 실제 voxel spacing을 이용해서 변환해줌.
	- phys_coords = origin + voxel_spacing * voxel_coord
![Screenshot from 2024-01-30 16-33-14](https://github.com/minyoungci/MedicalVideo/assets/80457917/9b8c2100-34f1-4d27-ab93-0a09c5959d8c)

#### Look Up Table(LUT)
- Modality LUT
	- Device에서 나온 pixel의 값 변환, Load할 때 값을 사용
- VOI LUT 
	- 원하는 조직의 영역을 보기 위해서 적용
- Presentation LUT
	- Device마다 영상을 Gray scale의 표현값을 설정. 

#### Histogram equalization
- 각 영상마다 pixel값의 분포를 넓게 해주면서 밝기를 변화시켜줌.
- ![Screenshot from 2024-01-30 16-35-31](https://github.com/minyoungci/MedicalVideo/assets/80457917/c621ea20-fb0f-4ec7-bd7f-8b21a1735baf)

