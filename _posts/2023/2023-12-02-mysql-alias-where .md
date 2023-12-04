---
layout: post
title:  "[MySQL] 별칭 부여 칼럼을 조건문에서 사용하기"
date:   2023-12-02 13:42:18 +0900
categories: 
    - dev
    - db
tag: Db
related_posts:
    - 
---

- Table of Contents
{:toc .large-only}

쿼리 작성 중 where 문에서 count(*)를 조건으로 사용해야하는 상황이 발생했다.

### SQL 구문실행 순서
FROM -> WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY
{:.message}
- 위의 순서로 실행이 되고 alias는 GROUP BY 이후부터 인식이 가능하다.


### 사용방법
- ailas 값을 사용하기 위해 GROUP BY 이후의 **HAVING**을 이용한 쿼리를 사용한다.

~~~sql
SELECT COUNT(*) AS CNT FROM USER HAVING CNT >= 3
~~~

