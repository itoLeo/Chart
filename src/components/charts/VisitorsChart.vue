<script>
// 折れ線グラフのテンプレート読み込み.extendsで再定義
import { Line } from 'vue-chartjs'

export default {
  // importでBar（棒）もしくはLine（折れ線）を読み込みextendsで表のタイプを定義
  extends: Line,
  name: 'VisitorsChart',
  data () {
    return {
      data: {
        labels: ['1月','2月','3月','4月','5月','6月','7月','8月','9月','10月','11月','12月'],
        datasets: [
          {
            type: 'line',
            // 本来チャートの上に表示されるラベルだが、optionのlegends/display:falseで非表示になっている
            label: '2020',
            data: [1,2,3,4,5,6,7,8,9,0,11,15],
            borderColor: "#7A3B00",
            // 線の丸みを消してカクカクさせる
            lineTension: 0
          }
        ],
      },
      options: {
        //アスペクト比を維持しない設定。これでこれでcssによるサイズ変更が可能になる（変更後リロード必要）
        maintainAspectRatio: false,
        // ラベルを非表示
        legend: {
          display: false
        }
      }
    }
  },
  mounted () {
    this.renderChart(this.data, this.options)
  }
}
</script>
