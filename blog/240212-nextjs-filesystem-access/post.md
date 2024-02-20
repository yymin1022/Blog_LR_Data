안녕하세요!<br>
대학생 1인개발자 LR입니다!

오늘도 가벼운 개발 삽질 해결 이야기를 다뤄보려고 합니다.

최근, 제가 대학교 입학 후 부터 쭉 임원진으로 활동중인 동아리 CECOM의 홈페이지 개발 프로젝트를 진행하고 있는데요,<br>
Next.JS를 기반으로 해서 제가 BE와 CI/CD 개발, 그리고 PM을 맡고있으며<br>
2명의 FE 개발자, 그리고 1명의 디자이너와 함께 개발을 진행하고 있습니다.

동아리 활동에 대한 게시글 저장을 목적으로 여러가지 사례를 분석하고,<br>
최종적으로는 현재 제 블로그와 마찬가지로 배포서버의 로컬 디렉토리에 저장하는 방향으로 결정하게 되었는데,<br>
테스트 환경에서는 문제없다가 막상 배포해보니 파일시스템 접근이 아예 불가능한 문제를 발견했고<br>
조금 전 문제를 막 해결한 참에, 그 내용을 한번 공유해보려고 합니다.

먼저 제가 파일시스템 접근을 의도하여 작성한 함수입니다.

```typescript
export const getProjectThumbnail = (projectID: string) => {
    const fileFullDir = `${process.env.FILE_DIR}/project/${projectID}/thumb.png`;
    let fileBuffer: buffer.Buffer | undefined;
    try {
        fileBuffer = fs.readFileSync(fileFullDir);
        return Buffer.from(fileBuffer!).toString("base64");
    }catch(e){
        return undefined;
    }
}
```

`fs` 모듈을 이용해서 파일시스템에 접근하도록 하는 함수인데요,<br>
결론부터 말씀드리자면 이 함수를 Client-Side 파트에 위치시킨 것이 문제가 되었습니다.

다시 생각해보면, 어찌보면 당연하게도 서버 로컬에 접근하는 함수를 Client-Side에 위치시킨 것이 어이가 없긴 합니다.

해당 코드를 기존의 위치에서 `/api` 디렉토리 내부의 `_utils` 디렉토리로 옮겨준 뒤 테스트를 해보니<br>
배포 환경에서도 의도한대로 잘 작동이 되네요.

조금의 구글링을 통해 배운 결과로는, Next.JS에서 `/api` 디렉토리는<br>
별도의 Client-Side로 컴파일되지 않고 Server-Side에서