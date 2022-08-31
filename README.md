## 2022 Samsung AI Challenge (Materials Discovery)
### (2022.08.08 ~ 2022.09.16 11:59)
### 주제 : 유기분자 구조로부터 Reorganization Energy를 예측하는 AI 알고리즘 개발

### 2차 시도
(mol_file에서 무언가를 얻어내는것 보다는 smiles을 활용하는것이 상당히 높은 가능성을 가지는것 같다.)
1. data
	1.1 SMILES 
		- NLP 처리 하여 tensor형태로 변환

2. modeling
	2.1 tensor -> GRU

# (15/450) with acc = 15.1

### 1차 시도
1. data
    1.1 SMILES (분자구조식)
		1.1.1 SMILES files -> to some tensor
			-> by rdkit (reference to 2021 Competition)
    1.2 .mol 파일 (status={ex,g}) 
        1.2.1 atom 개수 bond 개수 -> done
        1.2.2 atom들의 location, element_type (x,y,z,element_type) -> done
        1.2.3 bond결합 atom구조, (atom_1,atom_2,bond_type) -> done

2. modeling
	- (,2) :mol -> count
	- (,4) :mol -> location
	- (,3) :mol ->  bond
	- (,2048) : SMILES -> tensor
		- keras
		- pytorch

https://dacon.io/competitions/official/235789/codeshare/4043?page=1&dtype=recent


