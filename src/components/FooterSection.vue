<template>
  <footer id="footer" role="contentinfo">
    <div class="footer__inner">
      <h2 class="footer__text">
        <span>CHLOE CHOI</span>
        <span>PORTFOLIO_VITE</span>
      </h2>
      <div class="footer__info">
        <div class="left">
          <div class="title">
            <a href="#">sign up</a>
          </div>
          <p>회원가입을 하시면 댓글과 게시판 기능을 이용할 수 있습니다.</p>
        </div>
        <div class="right">
          <h3>social</h3>
          <ul>
            <li>
              <a href="https://github.com/chloe-20">github</a>
              <em>깃헙에 들어오시면 모든 소스를 볼 수 있습니다.</em>
            </li>                        
          </ul>
        </div>
      </div>
      <div class="footer__right">&copy; 2023 CHLOE_CHOI</div>
    </div>
  </footer>
</template>

<style lang="scss">
#footer {
  font-family: var(--mainKor-font);
}

.footer__inner {
  padding: 16px;

  .footer__text {
    font-size: 12px;
    border-top: 1px solid var(--black);
    border-bottom: 1px solid var(--black);
    display: flex;
    justify-content: space-between;
  }

  .footer__info {
    display: flex;
    justify-content: space-between;
    margin: 100px 0;

    @media (max-width: 768px){
      flex-direction: column;
    }

    .left {
      width: 40%;

      @media (max-width: 768px){
        width: 100%;
      }

      .title {
        border-top: 2px solid var(--black);
        border-bottom: 1px solid var(--black);
        padding: 20px 0;        
        font-weight: 700;
        background: url(@/assets/img/arrow.svg) no-repeat right 20px;
        transition: all 0.3s;

        &:hover {
          background-color: var(--black400);
          padding-left: 10px;
          border-color: transparent;
        }
      }

      .desc {
        font-size: 12px;
        padding-top: 20px;

        @media (max-width: 768px){
          margin-bottom: 40px;
        }
      }
    }

    .right {
      width: 50%;

      @media (max-width: 768px){
        width: 100%;
      }

      h3 {
        border-top: 2px solid var(--black);
        font-size: 10px;
        margin-bottom: 40px;
        padding-top: 10px;
      }

      ul {
        border-top: 1px solid var(--black);

        li {
          border-bottom: 1px solid var(--black);

          a {
            padding: 14px 0;
            font-size: 14px;
            display: inline-block;              
          }

          em {
            font-size: 12px;
            padding-left: 10px;
            opacity: 0;
            transition: all 0.3s;
          }

          &:hover {

            em {
              opacity: 1;
            }
          }
        }
      }
    }
  }

  .footer__right {
    text-align: center;    
    font-size: 12px;
    margin-bottom: 20px;
  }
}
</style>