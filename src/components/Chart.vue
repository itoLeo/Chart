<script>
import { Line } from 'vue-chartjs'

export default {
  // importでBar（棒）もしくはLine（折れ線）を読み込みextendsで表のタイプを定義
  extends: Line,
  name: 'chart',
  data () {
    return {
      data: {
        labels: ['1月','2月','3月','4月','5月','6月','7月','8月','9月','10月','11月','12月'],
        datasets: [
          {
            type: 'line',
            label: '入場者数履歴',
            data: [1,2,3,4,5,6,7,8,9,0,1],
            backgroundColor: 'rgba(60, 160, 220, 0.3)',
          }
        ],
      },
      options: {
        //アスペクト比を維持しない設定。これでこれでcssによるサイズ変更が可能になる（変更後リロード必要）
        maintainAspectRatio: false
      }
    }
  },
  mounted () {
    this.renderChart(this.data, this.options)
  }
}
</script>
