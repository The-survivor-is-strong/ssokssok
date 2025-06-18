# 📚 Zustand
Zustand 톺아보기

# ⏰ 스터디 일정
- 매주 수요일 오후 10시 진행
- OT : 6월 18일 (수)
- 스터디 진행 : 6월 18일 ~

## 📅 전체 학습 일정 (8주 계획)
> 💡 **학습 일정**    
> 
> 1주차: 핵심 상태 관리 로직    
> 2~3주차: 미들웨어 / 인핸서 심화 분석    
> 4주차: 구독 메커니즘    
> 5~6주차: 성능 최적화 분석 및 벤치마킹     
> 7~8주차: 실제 프로젝트 적용 및 사용 패턴 정리 


## 🎯 Zustand 핵심 기능별 학습 로드맵

### **1. 핵심 상태 관리 로직**

**🎯 학습 목표**

- Zustand의 `createStore` 함수 동작 원리 완전 이해
- 상태 업데이트 메커니즘과 불변성 처리 방식 파악
- vanilla JS에서의 상태 관리 구현 방식 이해


**📋 실행 계획**

```tsx
주요 파일 분석
- src/vanilla.ts (핵심 createStore 함수)
- src/index.ts (진입점)
- src/types.d.ts (타입 정의)

목표
1. vanilla.ts의 createStore 함수를 단계별로 분석
2. set, get 함수의 동작 방식 이해

```

**✅ 학습 완료 기준:**

- createStore 함수를 이해할 수 있다.
- vanilla JavaScript로 기본 상태 관리 구현 가능

### **2. 미들웨어/인핸서**

**🎯 학습 목표**

- 미들웨어 패턴과 함수 합성 방식 이해
- 각 미들웨어의 구현 원리 파악
- 커스텤 미들웨어 개발 능력 획득

**📋 실행 계획**

```tsx
주요 파일 분석
- src/middleware/persist.ts (상태 지속화)
- src/middleware/devtools.ts (Redux DevTools)
- src/middleware/immer.ts (불변성 관리)
- src/middleware/subscribeWithSelector.ts (선택적 구독)
- src/middleware/combine.ts (스토어 결합)

목표
1. 각 미들웨어의 고차 함수 패턴 분석
2. persist 미들웨어의 직렬화/역직렬화 로직 이해
3. devtools 미들웨어의 Redux DevTools 연동 방식 파악
4. 커스텀 미들웨어 3개 구현:
   - Logger 미들웨어
   - Undo/Redo 미들웨어
   - API 동기화 미들웨어

```

**✅ 학습 완료 기준**

- 미들웨어 체이닝 원리 설명 가능
- 실용적인 커스텀 미들웨어 개발 가능

### **3. 구독 메커니즘**

**🎯 학습 목표**

- 리스너 등록/해제 시스템 이해
- React의 useSyncExternalStore와의 연동 방식 파악
- 메모리 누수 방지 메커니즘 이해

**📋 실행 계획**

```tsx
주요 파일 분석
- src/vanilla.ts (subscribe 함수)
- src/react.ts (useStore 훅)
- tests/ 디렉토리의 구독 관련 테스트

목표
1. subscribe/unsubscribe 함수 동작 분석
2. React 컴포넌트에서 구독 생명주기 추적
3. 메모리 누수 시나리오 테스트
4. 커스텀 구독 훅 구현

```

**✅ 학습 완료 기준:**

- 구독자 목록 관리 방식 설명 가능
- React와 vanilla 환경에서 구독 메커니즘 차이점 이해

### **4. 성능 최적화 (재렌더링 방지)**

**🎯 학습 목표**

- Zustand가 "빠른" 이유 분석
- 선택적 구독과 얕은 비교 메커니즘 이해
- React 렌더링 최적화 전략 파악

**📋 실행 계획**

```tsx
주요 파일 분석
- src/shallow.ts (얕은 비교 함수)
- src/vanilla/shallow.ts (vanilla 얕은 비교)
- src/react.ts (useStore의 selector 로직)
- src/middleware/subscribeWithSelector.ts

성능 측정 과제
1. React DevTools Profiler로 리렌더링 측정
2. 다양한 selector 패턴의 성능 비교
3. shallow vs deep equality 성능 테스트
4. 대용량 상태에서의 성능 벤치마크
5. Redux, Context API와 성능 비교

최적화 기법 분석
- selector 함수의 메모이제이션
- 구독 범위 최소화
- 불필요한 리렌더링 방지 패턴

```

**✅ 학습 완료 기준**

- 성능 최적화 원리 5가지 이상 설명 가능
- 성능 측정 도구 활용 가능
- 실제 애플리케션에서 성능 개선 적용 가능

### **5. 사용 패턴/예시**

**🎯 학습 목표**

- 실제 프로젝트에서의 다양한 활용 패턴 습득
- 베스트 프랙티스와 안티 패턴 구분
- 복잡한 상태 관리 시나리오 해결 능력

**📋 실행 계획**

```tsx
분석 대상
- examples/ 디렉토리의 모든 예제
- docs/ 디렉토리의 사용법 문서
- tests/ 디렉토리의 실제 사용 시나리오

실습 프로젝트
1. Todo App (CRUD + 필터링)
2. Shopping Cart (복잡한 상태 계산)
3. 실시간 채팅 (WebSocket + 상태 동기화)
4. 폼 관리 (validation + 에러 핸들링)
5. 대시보드 (여러 데이터 소스 관리)

패턴 분석
- 상태 구조 설계 패턴
- 액션 함수 조직화 방법
- 여러 컴포넌트 간 상태 공유 전략
- 에러 처리 및 로딩 상태 관리
```

**✅ 학습 완료 기준**

- 5가지 이상의 실용적인 예제 구현 완료
- 복잡한 상태 관리 요구사항을 Zustand로 해결 가능
- 팀 프로젝트에 도입 가이드라인 작성 가능