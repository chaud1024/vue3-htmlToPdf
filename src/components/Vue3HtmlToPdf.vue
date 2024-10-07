<template>
  <div>
    <vue3-html2pdf
      :show-layout="false"
      :float-layout="true"
      :enable-download="true"
      :paginate-elements-by-height="1400"
      filename="hee hee"
      :pdf-quality="2"
      :manual-pagination="false"
      pdf-format="a4"
      pdf-orientation="portrait"
      pdf-content-width="800px"
      :html-to-pdf-options="htmlToPdfOptions"
      ref="html2Pdf"
    >
      <template v-slot:pdf-content>
        <section class="pdf-content">
          <!-- PDF Content Here -->
          <table class="report inslot">
            <tr>
              <th colspan="3" class="title">
                <h1>장애처리 진행상황 보고</h1>
              </th>
            </tr>
            <tr>
              <td colspan="3" class="subTitle">
                <h2>1. 장애 접수내용</h2>
              </td>
            </tr>
            <tr>
              <td>장치명</td>
              <td colspan="2">{{ gridItem.deviceNm }}</td>
            </tr>
            <tr>
              <td>점검 구분</td>
              <td colspan="2">{{ gridItem.maintTypeNm }}</td>
            </tr>
            <tr>
              <td>단계</td>
              <td colspan="2">{{ gridItem.maintPrcsNm }}</td>
            </tr>
            <tr>
              <td>완료여부</td>
              <td colspan="2">{{ gridItem.completeYn }}</td>
            </tr>
            <tr>
              <td colspan="3" class="subTitle">
                <h2>2. 장애내용</h2>
              </td>
            </tr>
            <tr>
              <th>장애내역</th>
              <th>장애일시</th>
              <th>담당자</th>
            </tr>
            <tr>
              <td rowspan="2">{{ gridItem.problem }}</td>
              <td>{{ gridItem.problemDt }}</td>
              <td>{{ gridItem.problemNm }}</td>
            </tr>
            <tr>
              <td colspan="3">
                <template v-if="gridItem.problemImg">
                  <img :src="gridItem.problemImg" />
                </template>
                <template v-else>
                  <span>noImage</span>
                </template>
              </td>
            </tr>
            <tr>
              <td colspan="3" class="subTitle">
                <h2>3. 점검내용</h2>
              </td>
            </tr>
            <tr>
              <th>점검내역</th>
              <th>점검일시</th>
              <th>담당자</th>
            </tr>
            <tr>
              <td rowspan="2">
                {{ gridItem.analyze }}
              </td>
              <td>{{ gridItem.analyzeDt }}</td>
              <td>{{ gridItem.analyzeNm }}</td>
            </tr>
            <tr>
              <td colspan="3">
                <template v-if="gridItem.analyzeImg">
                  <img :src="gridItem.analyzeImg" />
                </template>
                <template v-else>
                  <span>noImage</span>
                </template>
              </td>
            </tr>
            <tr>
              <td colspan="3" class="subTitle">
                <h2>4. 조치내용</h2>
              </td>
            </tr>
            <tr>
              <th>조치내역</th>
              <th>조치일시</th>
              <th>담당자</th>
            </tr>
            <tr>
              <td rowspan="2">
                {{ gridItem.resolve }}
              </td>
              <td>{{ gridItem.resolveDt }}</td>
              <td>{{ gridItem.resolveNm }}</td>
            </tr>
            <tr>
              <td colspan="3">
                <template v-if="gridItem.resolveImg">
                  <img :src="gridItem.resolveImg" />
                </template>
                <template v-else>
                  <span>noImage</span>
                </template>
              </td>
            </tr>
          </table>
        </section>
      </template>
    </vue3-html2pdf>
    <section class="pdf-content">
      <!-- PDF Content Here -->
      <table class="report">
        <tr>
          <th colspan="3" class="title">
            <h1>장애처리 진행상황 보고</h1>
          </th>
        </tr>
        <tr>
          <td colspan="3" class="subTitle">
            <h2>1. 장애 접수내용</h2>
          </td>
        </tr>
        <tr>
          <td>장치명</td>
          <td colspan="2">{{ gridItem.deviceNm }}</td>
        </tr>
        <tr>
          <td>점검 구분</td>
          <td colspan="2">{{ gridItem.maintTypeNm }}</td>
        </tr>
        <tr>
          <td>단계</td>
          <td colspan="2">{{ gridItem.maintPrcsNm }}</td>
        </tr>
        <tr>
          <td>완료여부</td>
          <td colspan="2">{{ gridItem.completeYn }}</td>
        </tr>
        <tr>
          <td colspan="3" class="subTitle">
            <h2>2. 장애내용</h2>
          </td>
        </tr>
        <tr>
          <th>장애내역</th>
          <th>장애일시</th>
          <th>담당자</th>
        </tr>
        <tr>
          <td rowspan="2">{{ gridItem.problem }}</td>
          <td>{{ gridItem.problemDt }}</td>
          <td>{{ gridItem.problemNm }}</td>
        </tr>
        <tr>
          <td colspan="3">
            <template v-if="gridItem.problemImg">
              <img :src="gridItem.problemImg" />
            </template>
            <template v-else>
              <span>noImage</span>
            </template>
          </td>
        </tr>
        <tr>
          <td colspan="3" class="subTitle">
            <h2>3. 점검내용</h2>
          </td>
        </tr>
        <tr>
          <th>점검내역</th>
          <th>점검일시</th>
          <th>담당자</th>
        </tr>
        <tr>
          <td rowspan="2">
            {{ gridItem.analyze }}
          </td>
          <td>{{ gridItem.analyzeDt }}</td>
          <td>{{ gridItem.analyzeNm }}</td>
        </tr>
        <tr>
          <td colspan="3">
            <template v-if="gridItem.analyzeImg">
              <img :src="gridItem.analyzeImg" />
            </template>
            <template v-else>
              <span>noImage</span>
            </template>
          </td>
        </tr>
        <tr>
          <td colspan="3" class="subTitle">
            <h2>4. 조치내용</h2>
          </td>
        </tr>
        <tr>
          <th>조치내역</th>
          <th>조치일시</th>
          <th>담당자</th>
        </tr>
        <tr>
          <td rowspan="2">
            {{ gridItem.resolve }}
          </td>
          <td>{{ gridItem.resolveDt }}</td>
          <td>{{ gridItem.resolveNm }}</td>
        </tr>
        <tr>
          <td colspan="3">
            <template v-if="gridItem.resolveImg">
              <img :src="gridItem.resolveImg" />
            </template>
            <template v-else>
              <span>noImage</span>
            </template>
          </td>
        </tr>
      </table>
    </section>
    <button @click="generateReport">Download PDF</button>
  </div>
</template>
<script setup>
import { ref } from 'vue'
import Vue3Html2pdf from 'vue3-html2pdf'

const html2Pdf = ref(null)

const generateReport = () => {
  html2Pdf.value.generatePdf()
}

const gridItem = {
  maintCd: 1,
  domainCd: 7,
  maintTypeCd: 'maintType002',
  maintPrcsCd: 'maintPrcs003',
  problem: '장애 발생',
  analyze: '장애 점검 진행',
  resolve: '교체 수리',
  problemDt: '2024-10-02 35:07:51',
  analyzeDt: '2024-06-22 23:07:45',
  resolveDt: '2024-08-31 38:03:39',
  problemNm: '관광과 김윤정',
  analyzeNm: '박 책임, 김 선임',
  resolveNm: '이 실장',
  problemImg:
    'data:image/gif;base64,R0lGODlhAAEAAcQAALe9v9ve3/b393mDiJScoO3u74KMkMnNz4uUmKatsOTm552kqK+1uNLW18DFx3B7gP///wAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACH/C1hNUCBEYXRhWE1QPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4gPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS4wLWMwNjAgNjEuMTM0Nzc3LCAyMDEwLzAyLzEyLTE3OjMyOjAwICAgICAgICAiPiA8cmRmOlJERiB4bWxuczpyZGY9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkvMDIvMjItcmRmLXN5bnRheC1ucyMiPiA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtbG5zOnhtcD0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wLyIgeG1wTU06T3JpZ2luYWxEb2N1bWVudElEPSJ4bXAuZGlkOjAxODAxMTc0MDcyMDY4MTE5QjEwQjYyNTc4MkUxRURBIiB4bXBNTTpEb2N1bWVudElEPSJ4bXAuZGlkOjEzN0VEMDZBQjMyNzExRTE4REMzRUZGMkFCOTM1NkZBIiB4bXBNTTpJbnN0YW5jZUlEPSJ4bXAuaWlkOjEzN0VEMDY5QjMyNzExRTE4REMzRUZGMkFCOTM1NkZBIiB4bXA6Q3JlYXRvclRvb2w9IkFkb2JlIFBob3Rvc2hvcCBDUzUgTWFjaW50b3NoIj4gPHhtcE1NOkRlcml2ZWRGcm9tIHN0UmVmOmluc3RhbmNlSUQ9InhtcC5paWQ6MDI4MDExNzQwNzIwNjgxMTlCMTBCNjI1NzgyRTFFREEiIHN0UmVmOmRvY3VtZW50SUQ9InhtcC5kaWQ6MDE4MDExNzQwNzIwNjgxMTlCMTBCNjI1NzgyRTFFREEiLz4gPC9yZGY6RGVzY3JpcHRpb24+IDwvcmRmOlJERj4gPC94OnhtcG1ldGE+IDw/eHBhY2tldCBlbmQ9InIiPz4B//79/Pv6+fj39vX08/Lx8O/u7ezr6uno5+bl5OPi4eDf3t3c29rZ2NfW1dTT0tHQz87NzMvKycjHxsXEw8LBwL++vby7urm4t7a1tLOysbCvrq2sq6qpqKempaSjoqGgn56dnJuamZiXlpWUk5KRkI+OjYyLiomIh4aFhIOCgYB/fn18e3p5eHd2dXRzcnFwb25tbGtqaWhnZmVkY2JhYF9eXVxbWllYV1ZVVFNSUVBPTk1MS0pJSEdGRURDQkFAPz49PDs6OTg3NjU0MzIxMC8uLSwrKikoJyYlJCMiISAfHh0cGxoZGBcWFRQTEhEQDw4NDAsKCQgHBgUEAwIBAAAh+QQAAAAAACwAAAAAAAEAAQAF/yAkjmRpnmiqrmzrvnAsz3Rt33iu73zv/8CgcEgsGo/IpHLJbDqf0Kh0Sq1ar9isdsvter/gsHhMLpvP6LR6zW673/C4fE6v2+/4vH7P7/v/gIGCg4SFhoeIiYptBQEADAQED5OUlQ8DkQwAAQKLni0KDgsDlqWmpQYLDgqfrSINCQans7SWBgkNrogFDKS1v8APBgwFuoIBksHKwQsBxn3Iy9LKBM7PdwXJ09vAC8XXcwDc48EDAOBwCgjk7MAI3+hqB77t9bMDufFoDPb9tef6yiTwR3BWgoBiBKwryLDUQYRftDWcOOkhxC0DKWqseFGLuI0gHXS80gCkyQfWRv9KKUDvJMUBnVRGkeiS4gKZUA7UPJkP5xIBLXdSNOCTyUehIAEWPQIUqUmYS48cdbrxQFQjsqiCJHp1SEmtJlN2/ZER7EaLY30ENdtwQNofAdiaZPWWx1S5E0XW3UETL8Obe3Ws9UuQa+AbAghvPIwjrmKKYhnLcPy4YWTJMBxUntgTc4y7m/sp9QwDdOh6o0m7MH2aXWrVLFi3HmcV9ouvs+1dtp2Ccu52u3mfKPDbXkzhLIrXQ+5ioXJuBJi34PecGwPpLHRW39YZ+4nE26cd947CeXhg0cmr0Hw+WG31JQQ4AFC2fS1NB8aTVzDY/q8BdJHXlH/bQEUeewRuo5f/d30lGEx63jnIjVvkSciNehZug2GG0mzIoTIefgiMelmJWAuE2DVooiUoSkfdirO8hpx2MJ7yHnYK1DgLPN71B6Nh5NWn4yTXwefbkA8ESCKSkyAA3wg0DnkjfCXW6OSTIxy5YnBB6lgkliMoBCMC+oHJkolkgjmceRKmqeZ3APi4nTlvriDAAQCo+BsBADRQZp0o4LYdl4CiIOdpQBY6XXhfKgpKeDw6ygKbubUo6QpR/jblpSscqliinK4gW2UyhooCcb8ZaGoLQoaG1qoroDpbpLCq0Opjr9aqgqyh0aprCrf6Veqv33lKlarExrbZgsm2UCVeVzbrgpZsESqt/wkLEJbrtSqMihSz3K5ArVbWhjsCr2z9ae4JhK3bHF6WunuCnkIBJq8KL5o17L0ieFvTvvz661J3/JYwLlLlynuwUAm7u/BODa/7cE0RmzuxSxWHe/FJGXO7cVgFp5ApuSGjIPBJAN8bLFKNljzCs1pF67II6JqlbsCEgRvygHghW7CYirlZsDqbvVNwA8ZqhY+8BWSb2wI36xqncnRKewDMvxmwqalX+1cNrF07+PWlYWeodaHyYW2hAQ5EjRwvSSc4ADHqBeA0k5Qk0PFYd6qNt9Zuv6VAAnEPOUACSu51J6V4/0LA1lENXnjjlhyeOE6LU24PAvnhFMDKmo9z+P/euzjgd+j1sO2rKw3cjfpGCxC8CNyv72QAAKsTUgDotYOUQO6AnNz7RinrUQDjwyMlNCD8Jd/z5XsEMLnzGwH4x8fUu2Q9H81nT9j2eZzpvWI+0wH0+EHnwTv6WrUsh6DsK0Z6GDzH/2ng+9gfWvFm1Ky/XwMAHhrW9z+t8G8M4ClgZconDwWGBnJocJ0DCWOvNkxwMxRixAU3g78wYG+DFHOD8EBYE53lj4SEOWBEUEiYeJ3hdCwUiszUEMN2sSFHNcSLAMMAvxySbA0j9KFGVMgFAgoRJO4zA72OeBIXkmF6TCwIqMqQwChSZQ0ftCJD5leFkWmxJrIbQxC/SBD/ImZBgmR0ybbGsMQ0TsSJYXAjUjLYPzkipYNayKId68FFKSBojyeB4BfGCEjXoKGNhfRHBcmAvEQyBI5ecKRLzoBDSYJkh3m0JMjKQEhNTsOEX8iXJxtiRiogcpTkgOQWYIhKdswwjq2kSBn0GEtlQK8LPaxlP/rYhE7q8heljMIff9kPUHLBf8RkByaxgMZkjmOR9GOlM39hADxigWjT5AYCbkm/ZmazFlBjA9K+CYyluUEAUyOnKcxhzYSYTp2UYFs7zdA6csaOD3fypicX0DlACAAW0iTjLfxUugUENIepcMAyBVGAA0DCigRgwAEWqggF4IkAB82eAfh0AG5eaCQAeFrAKSlHgAUA4AC8DIgAAtCAR0QCb5noEyfgo4AAOMKlBGhkaxAQ000EwKOSqqlN8QSAooo0EpHQKTl4itSSFrWoKLUpUGdG1apa9apYzapWt8rVrnr1q2ANq1jHStaymvWseggBADs=',
  analyzeImg: '',
  resolveImg: '',
  completeYn: 'Y',
  deleteYn: 'N',
  deviceCd: '',
  deviceNm: '계수기3',
  insertDt: '2024-08-09 58:02:41',
  insertId: 'a',
  insertNm: '유지보수 담당자',
  updateDt: '2024-07-29 06:10:21',
  updateId: 'a',
  updateNm: '유지보수 담당자',
  domainNm: '교통시스템',
  maintTypeNm: '정기 점검',
  maintPrcsNm: '현장 방문'
}

// PDF 생성 옵션 설정
const htmlToPdfOptions = {
  margin: [10, 10],
  filename: 'hehehe.pdf',
  image: {
    type: 'png',
    quality: 0.98
  },
  enableLinks: false,
  html2canvas: {
    scale: 1,
    useCORS: true
  },
  jsPDF: {
    unit: 'mm',
    format: 'a4',
    orientation: 'portrait'
  }
};
</script>
<style>
.report {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 20px;
  background-color: #fff;

  &.inslot {
    padding: 50px;
  }

  > * {
    color: #242C2A;
    word-break: keep-all;
  }

  h1 {
    font-size: 20px;
  }

  h2 {
    font-size: 16px;
  }

  th, td {
    border: 1px solid #e6e6e6;
    padding: 8px;
    text-align: left;
    box-sizing: border-box;
  }

  tr {
    th {
      width: 30%;
    }
  }

  td {
    img {
      width: 350px;
      height: auto;
    }
  }

  .title {
    background-color: #cdcdcd;
  }
  .subTitle {
    background-color: #f1f1f1;
  }

  .responsibility {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }
}
</style>