# categorizefile

EXIF 기반 파일 분류(동영상 파일도 가능한지 확인요망)

Base
    하기 EXIF 기준으로 파일을 분류하며 순서는 다음과 같다.
        BASE EXIF
        1. DateTimeOriginal
        2. DateTimeDigitized
        3. DateTime

    확장자 필터
        - jpg/jpeg/png/gif 등
        - mp4/mov/mkv/avi 등

    -- 이건 나중에 하자
    분류할 파일이 특정 디렉토리 하위에 모두 있는 경우 다음과 같이 분류한다.
        1. EXIF 기반으로 연도별 폴더 생성
        2. 연도 폴더 내부 연도_월(YYYY_MM) 형태의 월별 폴더 생성(12개)
        3. 파일의 현재 디렉토리와 이동할 최종 디렉토리를 가져온다.
            (1) EXIF 기반으로 최종 디렉토리 구함
            (2) (1)이 없는 경우 파일명 기반으로 최동 디렉토리 구함
        4. 월폴더에 파일이 없는 경우 해당 폴더 삭제

    분류할 파일이 이미 연도별 폴더로 나뉘어져 있는 경우 다음과 같이 분류한다.
        1. 연도 폴더 내부 연도_월(YYYY_MM) 형태의 월별 폴더 생성(12개)
        2. 파일의 현재 디렉토리와 이동할 최종 디렉토리를 가져온다.
            (1) EXIF 기반으로 최종 디렉토리 구함
            (2) (1)이 없는 경우 파일명 기반으로 최동 디렉토리 구함
        3. 월폴더에 파일이 없는 경우 해당 폴더 삭제
