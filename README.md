# HypergraphSurvey

## Code Structure
```
.
├── code/
│   ├── ktruss/                   # hyper k-truss 원본 코드
│   ├── nbr-kd-coreness/          # nbr-k-core, kd-core 원본 코드
│   ├── data_parser.py            # https://www.cs.cornell.edu/~arb/data/ 에서 데이터 다운 이후 network.hyp 파일 생성
│   ├── etc.py                    # 각종 기타 코드
│   ├── eval.py                   # 평가 지표 코드
│   ├── ex.py                     # 예시 도출 코드 (ex 폴더에 예시에 대한 결과 저장)
│   ├── func.py                   # 각종 기타 코드
│   ├── hyper_k_truss.py          # hyper k-trussness 저장 내역에서 truss 찾기
│   ├── hyper_k_trussness.py      # hyper k-trussness 실행 코드
│   ├── k_hypercore.py            # k-hypercoreness 저장 내역에서 core 찾기
│   ├── k_hypercoreness.py        # k-hypercoreness 실행 코드
│   ├── kab_truss.py              # kab-truss 실행 코드
│   ├── kg_core.py                # kg-core 실행 코드
│   ├── kg_coreness.py            # kg-coreness 실행 코드
│   ├── kgp_core.py               # kgp-core 실행 코드
│   ├── kinout_truss.py           # kinout-truss 실행 코드
│   ├── kq_core.py                # kq-core 실행 코드
│   ├── ks_core.py                # ks-core 실행 코드
│   ├── kt_hypercore.py           # kt-hypercoreness 저장 내역에서 core 찾기
│   ├── kt_hypercoreness.py       # kt-hypercoreness python 코드 (원본을 가져와서 정리한 것)
│   ├── main.py                   # 전체 실행 코드
│   ├── nbr_kd_core.py            # nbr-k-coreness, kd-coreness 저장 내역에서 core 찾기
│   ├── nbr_kd_coreness.py        # nbr-k-coreness, kd-coreness C++ 코드 call
│   ├── prefix_tree.png           # hyper k-truss에서 활용하는 Prefix tree 시각화
│   ├── stat.py                   # Data infomation
│   ├── stat.txt                  # Data infomation
├── datasets/
│   ├── ex/
│          ├── core/              # core 예제 파일 저장
│          ├── truss/             # truss 예제 파일 저장
│   ├── kab_clique/               # kab-truss에서 활용되는 clique expansion graph 저장
│   ├── kab_proj/                 # kab-truss에서 활용되는 projection graph 저장
│   ├── kt_pre/                   # kt-hypercore에서 활용되는 graph data 저장
│   ├── real/                     # real-world datasets
├── ex/
│   ├── parameters/               # 예제 설정을 위한 paramter 세팅
│   ├── results/                  # 예제 실행 후 결과 파일
├── output/                       # coreness 저장되어있음
```
- 다른 실행 결과 파일은 모르겠고 가장 최근 파일은 running_result.csv로 추정됨
- ../output/time.csv에 time이 저장되지 않은 coreness는 실제 coreness를 구하고, 저장되어있는 경우에는 저장된 coreness.csv + time.csv에 저장된 time 불러와서 return

## Arguments
| Parameter      | Description                                       |
|----------------|---------------------------------------------------|
| `--algorithm`  | Algorithm to use (ex. 'kg') | 
| `--mode`       | Mode (ex. 'param_select' / 'hyperedge_save') | 
| `--network`    | Relative path to dataset inside `datasets/` (ex. 'real/contact') | 
| `--k`          | Value of k (k-hypercore, nbr-k-core, kd-core, kt-hypercore,<br> kq-core, kg-core, kgp-core, ks-core, kab-truss, hyper k-truss) | 
| `--s`          | Value of s (ks-core) | 
| `--c`          | Value of c (ks-core) | 
| `--g`          | Value of g (kg-core, kgp-core) | 
| `--p`          | Value of p (kgp-core) | 
| `--t`          | Value of t (kt-hypercore) | 
| `--d`          | Value of d (kd-core) | 
| `--q`          | Value of q (kq-core) | 
| `--a`          | Value of a (kab-truss) | 
| `--b`          | Value of b (kab-truss) | 
| `--inn`        | Value of inn (k_{in}k_{out}-truss) | 
| `--out`        | Value of out (k_{in}k_{out}-truss) | 
| `--output`     | Output path (ex. '../output/running_results.csv') | 

