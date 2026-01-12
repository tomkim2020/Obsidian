==ssh -p 22 kth@10.10.50.52== : ssh [사용자ID]@[서버IP] 
==su -== : (Switch User) - 는 root의 환경 변수까지 모두 가져오겠다는 의미

==lsblk== (List Block Devices) : 물리 디스크 확인
==df - h== (Disk Free) : -h는 사람이 읽기 편한 단위(GB, TB)로 보여달라는 옵션
==apt update== : 업데이트 확인
==cat /etc/os-release== version 확인
==hostnamectl== 커널 버전, 아키텍처, OS 정보를 요약