# Installation for Windows


## 1. Git for Windows 설치
- Git-2.51.1-64-bit.exe:  bash 명령어 사용하기 위해 설치
- bash 명령어를 사용할 수 있는 다른 tool 이 설치되어있다면 설치할 필요 없음

## 2. Nodejs 설치
- claude code 를 사용하기 위해 claude code 에서 권장하는 Nodejs 버전 설치
- A. 인터넷이 가능한 환경일 경우, 
	- Nodejs 공식 홈페이지에 있는 최신 LTS 설치
	- https://nodejs.org/en/download/current
- B. 인터넷 사용이 자유롭지 않다면(내부망 사용 등)
	- github repository 에 올려져 있는 [node-v22.21.0-x64.msi](https://github.com/siyoungoh/install-claude-code/blob/master/node-v22.21.0-x64.msi "node-v22.21.0-x64.msi") (2025-10-26 기준) 설치
- 
## 3. Claude code 설치
- A. 인터넷이 가능한 환경일 경우,  
	- `npm install -g @anthropic-ai/claude-code` 로 claude code 최신 버전 설치
- B. 인터넷 사용이 자유롭지 않다면(내부망 사용 등),
	- claude-offline-bundle.tar.gz (https://github.com/siyoungoh/install-claude-code/blob/master/claude-offline-bundle.tar.gz) 다운로드
	- 압축 해제 후, 현재 위치를 `claude-offline` 폴더로 이동.
		- 예 `cd /path/to/claude-offline`
	- 먼저 Claude Code 패키지와 캐시 폴더가 같은 경로에 있는지 확인함.
```md
claude-offline/
├── anthropic-ai-claude-code-2.0.xx.tgz
└── cache/
    ├── npm-xxxx
    ├── npm-yyyy
```
- cache 폴더는 삭제하면 안됨.
- 오프라인 설치 명령어 실행
````bash
npm install -g ./anthropic-ai-claude-code-2.0.xx.tgz --offline --cache ./cache
````
- `-g` : 전역(global) 설치  
- `--offline` : 외부망(`registry.npmjs.org`)으로 접근하지 않음  
- `--cache ./cache` : 이미 준비된 캐시 폴더만 사용  
- → 이 명령 하나로 오프라인 환경에서 Claude Code가 설치됨.
