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
      }
    }
  },
  mounted () {
    this.renderChart(this.data, this.options)
  }
}
</script>
