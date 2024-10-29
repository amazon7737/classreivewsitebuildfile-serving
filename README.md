# **README - Ver 1.0 (창업동아리 단계)**

---

## **프로젝트 개요**  
SLR(Sharing Lecture Review)의. **Ver 1.0**에서는 Figma를 통한 와이어프레임을 개발하고 **React와 Redux**를 사용해 **프로토타입**을 구현하는데 중점을 두었습니다.

---

## **완성된 프로토타입**

<div align="center" style="display: flex; justify-content: center; gap: 20px;">

  <div>
    <img src="https://github.com/user-attachments/assets/25ab436f-937b-42b9-afde-d9385071a4b6" alt="프로토타입 메인 화면" width="400"/>
    <p align="center">프로토타입 메인 페이지</p>
  </div>

  <div>
    <img src="https://github.com/user-attachments/assets/abd7c5ad-916d-40ad-861e-ca94974adfb8" alt="프로토타입 수업 상세 페이지" width="400"/>
    <p align="center">수업 상세 페이지</p>
  </div>

</div>



---

## **주요 기능**  
- CRA(Create React App)을 활용한 프로젝트 프로토타입 구현  
- **JWT**와 **redux-persist**를 사용해 **localStorage에 쿠키 저장** 및 **전역 상태 유지**  
- **Axios**를 활용해 백엔드 API와 연동하여 **사용자 리뷰에 대한 CRUD** 기능 구현  

---

## **개선 및 회고**

### **프로젝트 초기: 문제 발견**  

1. **CRA의 성능 제약**  
   - 방대한 대학 데이터를 효율적으로 처리하기 위해 SSR(Server-Side Rendering)이 필요했습니다. 그러나 CRA는 SSR을 지원하지 않아 초기 로딩 속도가 느려졌습니다.

2. **SEO 최적화 필요성**  
   - 대학 플랫폼의 특성상 **검색 유입**이 중요했으나, CSR(Client-Side Rendering)만으로는 **SEO 최적화**가 제한적이었습니다. 이를 개선하기 위해 SSR 도입이 필수적이었습니다.

3. **비효율적인 컴포넌트 구조**  
   - 컴포넌트 간 의존성이 높아 **유지보수성**이 떨어졌으며, 작은 수정에도 **광범위한 코드 변경**이 필요했습니다.

4. **API 호출 분산 및 코드 중복 문제**  
   - API 호출이 **분산**되면서 비일관적인 **에러 처리**와 **중복 코드**가 발생했습니다. 이는 코드의 **가독성과 유지보수성**을 저하시켰습니다.

5. **JWT와 Redux-persist 사용 시 문제 발생**  
   - **Redux-persist**를 사용해 **localStorage**에 JWT를 저장하는 과정에서 **보안 문제**가 발생했습니다.
     - **로컬 스토리지에 저장된 토큰**은 **XSS(Cross-Site Scripting) 공격**에 취약했습니다.
   - 이러한 문제를 해결하기 위해 **HTTP-Only 쿠키**를 사용한 인증 방식으로의 전환을 검토했습니다.

---

## **향후 개선 방향**  
- **Next.js**로 전환해 **SSR과 SEO 최적화**를 통해 성능을 개선하고, **검색 유입**을 극대화  
- **Zustand**와 같은 경량 상태 관리 라이브러리 도입 검토  
- **Axios 인스턴스**를 활용해 API 호출을 중앙화하고, 일관된 에러 처리를 구현  
- **HTTP-Only 쿠키**와 같은 **보안 강화된 인증 방식** 도입 검토  

---

## **배운 점**  

1. **Redux를 활용한 전역 상태 관리**  
   - 복잡한 상태를 효율적으로 관리하기 위해 **Redux**를 도입해 전역 상태를 유지했습니다. 하지만 복잡한 설정과 코드량이 많아 경량화된 상태 관리 도구의 필요성도 느꼈습니다.

2. **Axios를 활용한 API 호출 및 데이터 연동**  
   - 백엔드와의 통신에서 **Axios**를 사용해 **CRUD 기능**을 구현했습니다. 이 과정에서 길어지는 코드에 대한 **API 호출 모듈화**의 중요성을 깨달았습니다.

3. **컴포넌트 설계의 중요성**  
   - 초기 설계에서 컴포넌트 간 의존성이 높아 유지보수가 어려웠습니다. 이를 통해 **컴포넌트의 재사용성과 독립성**을 고려한 설계가 필수적임을 배우게 되었습니다.

4. **JWT 보안 강화 필요성**  
   - **redux-persist**로 JWT를 **localStorage**에 저장했을 때 **보안 취약성**을 발견했습니다. 이를 해결하기 위해 **HTTP-Only 쿠키**와 같은 보안 강화된 인증 방식이 필요함을 인지했습니다.

5. **SSR 도입과 SEO 최적화의 필요성**  
   - **CRA 환경**에서는 **CSR**만으로는 초기 로딩 속도와 **SEO** 최적화가 제한적임을 체감했습니다. 이를 개선하기 위해 **Next.js**를 도입해 SSR과 SEO를 병행하는 것이 필수적임을 깨달았습니다.
