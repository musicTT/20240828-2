import streamlit as st

# Define MBTI descriptions
mbti_descriptions = {
    'ISTJ': 'ISTJ 유형은 책임감이 강하고 실용적이며 신뢰할 수 있는 사람입니다. 일에 대해 신중하고 세부 사항에 주의를 기울입니다.',
    'ISFJ': 'ISFJ 유형은 친절하고 책임감이 강하며 타인을 돕는 것을 즐깁니다. 신뢰할 수 있는 사람으로, 세심한 배려를 보입니다.',
    'INFJ': 'INFJ 유형은 직관적이고 감정적으로 깊이 있는 사람입니다. 비전을 가지고 있으며 사람들의 잠재력을 이해하고 싶어합니다.',
    'INTJ': 'INTJ 유형은 분석적이고 전략적인 사고를 하는 사람입니다. 독립적이며 목표를 달성하기 위해 체계적으로 계획합니다.',
    'ISTP': 'ISTP 유형은 실용적이고 즉흥적인 문제 해결자입니다. 물리적 도구나 기술을 다루는 데 능숙하며, 독립적입니다.',
    'ISFP': 'ISFP 유형은 예술적이고 감정적으로 개방적인 사람입니다. 현재의 순간을 즐기며, 자신의 감정을 표현하는 데 유능합니다.',
    'INFP': 'INFP 유형은 이상적이고 상상력이 풍부한 사람입니다. 내면의 가치와 목표를 중요시하며, 깊은 감정을 가지고 있습니다.',
    'INTP': 'INTP 유형은 논리적이고 분석적인 사고를 하는 사람입니다. 지적 호기심이 강하며, 문제 해결과 새로운 아이디어에 관심이 많습니다.',
    'ESTP': 'ESTP 유형은 활동적이고 모험을 즐기는 사람입니다. 현장 중심의 사고를 하며, 문제를 해결하기 위해 직접 행동하는 것을 좋아합니다.',
    'ESFP': 'ESFP 유형은 사교적이고 현실적인 사람입니다. 타인과의 교류를 즐기며, 현재의 순간을 최대한 즐기려고 합니다.',
    'ENFP': 'ENFP 유형은 열정적이고 창의적인 사람입니다. 새로운 아이디어와 가능성에 관심이 많으며, 다른 사람들과의 관계를 소중히 여깁니다.',
    'ENTP': 'ENTP 유형은 창의적이고 도전적인 사고를 하는 사람입니다. 새로운 아이디어와 해결책을 찾는 데 능숙하며, 논쟁을 즐깁니다.',
    'ESTJ': 'ESTJ 유형은 조직적이고 현실적인 사람입니다. 규칙과 구조를 중시하며, 목표를 달성하기 위해 체계적으로 일을 처리합니다.',
    'ESFJ': 'ESFJ 유형은 사교적이고 타인을 도와주는 것을 좋아하는 사람입니다. 안정성과 조화를 중시하며, 사람들 사이에서 조화로운 관계를 유지하려고 합니다.',
    'ENFJ': 'ENFJ 유형은 따뜻하고 지도력을 발휘하는 사람입니다. 다른 사람들을 격려하고 지원하며, 공동의 목표를 위해 노력합니다.',
    'ENTJ': 'ENTJ 유형은 전략적이고 결단력이 있는 사람입니다. 목표를 달성하기 위해 체계적으로 계획하며, 리더십을 발휘하는 것을 선호합니다.',
}

st.title('MBTI 성격 설명 서비스')

# Get user input
name = st.text_input('이름을 입력해주세요 : ')
mbti = st.selectbox('MBTI 유형을 선택해주세요:', list(mbti_descriptions.keys()))

# Check if the name field is not empty and button is clicked
if st.button('성격 설명 보기'):
    if name:
        description = mbti_descriptions.get(mbti, '선택된 MBTI 유형에 대한 설명이 없습니다.')
        st.write(f'{name}님, 선택한 MBTI 유형은 {mbti}입니다. 이 유형에 대한 설명은 다음과 같습니다:')
        st.write(description)
    else:
        st.write('이름을 입력해주세요!')
