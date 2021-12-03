# 검토에 사용된 SW

# Colab에서 알파 폴드를 실행하기 위한 설정

스파이크 단백질의 아미노 시퀀스가 길어서 메모리 오류가 발생하기 때문에 아래 설정을 통해 메모리 오류를 방지함

Colab Pro 가입 권장

```jsx
Here's what's in my .bashrc to work locally using https://github.com/YoshitakaMo/localcolabfold -

export NVIDIA_VISIBLE_DEVICES='all'
export TF_FORCE_UNIFIED_MEMORY='1'
export XLA_PYTHON_CLIENT_MEM_FRACTION='4.0'
And this worked on colabfold -- I added this cell to the top of the advanced notebook.

!nvidia-smi
%env TF_FORCE_UNIFIED_MEMORY=all
%shell echo $NVIDIA_VISIBLE_DEVICES
%env TF_FORCE_UNIFIED_MEMORY=1
%shell echo $TF_FORCE_UNIFIED_MEMORY
%env XLA_PYTHON_CLIENT_MEM_FRACTION=4.0
%shell echo $XLA_PYTHON_CLIENT_MEM_FRACTION
The 1460-residue (1 recycle only) test prediction on colab peaked at 15.9 GB GPU and 9.5 GB system RAM... not a ton of headroom to go for larger complexes, and it is slow. The free credit on google cloud compute is enough to see what more GPU RAM can do for you.

```

알파폴드를 실행하기 위한 노트북

[https://github.com/leahsol/deephope/blob/main/AlphaFold2_Colab.ipynb](https://github.com/leahsol/deephope/blob/main/AlphaFold2_Colab.ipynb)

# PyMol에서 겹쳐 보이기

[pymol 다운로드 하기](https://pymol.org/2/)

console에서 align명령어 사용해서 두 단백질을 겹쳐 보기

```jsx
PyMol>align 6vyb, 7dx1
```

[pymol사용법](https://www.youtube.com/watch?v=wiKyOF-pGw4&t=75s)

# Deeppurpose 실행

[https://github.com/leahsol/deephope/blob/main/DeepPurpose.ipynb](https://github.com/leahsol/deephope/blob/main/DeepPurpose.ipynb)

# Colab에서 Deepchem 실행하기

```jsx
!wget -c https://repo.anaconda.com/archive/Anaconda3-2019.10-Linux-x86_64.sh
!chmod +x Anaconda3-2019.10-Linux-x86_64.sh
!bash ./Anaconda3-2019.10-Linux-x86_64.sh -b -f -p /usr/local
!conda install -y -c deepchem -c rdkit -c conda-forge -c omnia deepchem-gpu=2.3.0
import sys
sys.path.append('/usr/local/lib/python3.7/site-packages/')
import deepchem as dc
```

# 기타 도구들

- [RDKit](https://www.notion.so/RDKit-Open-Source-Cheminformatics-Software-094323afc4e04fd886c97e6027c841dc)
- CellProfiler [https://cellprofiler.org/](https://cellprofiler.org/)
- 치료제 개발을 위한 컴퓨터 리소스 공유 [https://foldingathome.org/?lng=ko-KR](https://foldingathome.org/?lng=ko-KR)