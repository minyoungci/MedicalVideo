# DICOM - Digital Imaging and Communications in Medicine

메디컬 이미지의 차이점 
- 의료 영상의 제조사 마다 파일이 정량화 되어지지 않았음.
- 영상에 많은 정보가 필요함. (나이, 환자정보, 영상획득 정보)
	- 모든 사람마다 다른 정보를 가지고 있음.
- 이미지의 용량이 크기 때문에 압축이 필요함
	- Pathology : 10000x10000 image resolution
	- MRI images : 512x512x256 image size 
- 같은 영상이라도 영상의 의미가 다르기도 함. 

## DICOM - Digital Imaging and Communications in Medicine

- DICOM 파일을 열어보면 2000개의 정형화된 기준들이 있음.
	- 환자이름, 정보, 나이부터 병명, 및 위치

- 정보들의 경우 Information Object Definitions (IODs)로 표현을 한다.
	- 예를 들어 환자의 이름, 나이, 성별, 무게 등 다양한 속성들을 Binary로 저장할 수 있음

- 하지만 IOD를 저장후 DICOM을 다른 device로 보낼 경우 이미지가 유실될 수 있다.
	- Dicom Server Element(DIMSE) : IOD를 가지고 할 수 있는 행위 (저장, 찾기, 전송, 만들기, 가져오기)

- 최종적으로 Service-Object Pair(SOP) = IOD + DIMSE class를 가지고 동작이 되어진다.
-
- ![Screenshot from 2024-01-29 14-59-02](https://github.com/minyoungci/MedicalVideo/assets/80457917/2780df6e-a192-4084-a696-b13252a9f675)


- Dicom **Meta data**의 많은 정보는 DICOM data Dictionary를 통해서 해석이 가능함
	- Tag : Group, element 로 나뉘어지며 유사한 내용이 있으면 전자로 묶여진다.
	- **Attribute : Meta 데이터의 실제 값**
	- value representations (VR) : 나타내고자 하는 데이터의 정의, 데이터의 길이가 들어가 있음. 
		- 작성되는 데이터의 길이 (Text) : CS, SH, LO, ST, LT, UT 
		- 시간을 나타낼 때(dates): DA, TM, DT, AS 
		- Binary Format : AE(application, UI(Unique identifiers))
	- Value Multiplicity(VM): 다양한 값들이 들어갈 수 있는지 (1-n or n)
 - ![Screenshot from 2024-01-29 15-04-31](https://github.com/minyoungci/MedicalVideo/assets/80457917/e1028c6e-36c2-4767-be71-a0ef05c9c143)
- 이러한 과정을 거쳐서 encoding이 전체적으로 완료됨
	- DICOM unique identifiers are strings such as "1.2.840.10008.1.2"
	- ex. <patient ID> , <study ID>, <current data>, <current time in milliseconds>


 

















