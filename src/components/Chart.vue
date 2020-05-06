<script>
import { Bar } from 'vue-chartjs'

export default {
  extends: Bar,
  name: 'chart',
  data () {
    return {
      data: {
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
