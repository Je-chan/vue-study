# Composition API

## 1. setup()

- setup 에서 선언되는 변수는 반응성이 없다
- `import {ref} from 'vue'` 로 가져오는 ref 를 사용해서 선언하면 반응성을 가질 수 있다
- 단, ref 는 객체를 반환하기에 선언된변수명.value 로 반응성을 지니는 값을 가져올 수 있다.
- 정의된 데이터를 반환하고 template 에서 사용할 때는 .value 를 붙이지 않아도 된다
