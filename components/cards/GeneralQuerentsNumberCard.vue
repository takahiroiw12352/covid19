<template>
  <v-col cols="12" md="6" class="DataCard">
    <time-bar-chart
      :title="$t('新型コロナウイルスに関する一般相談件数')"
      :title-id="'number-of-general-querents'"
      :chart-id="'time-bar-chart-number-of-general-querents'"
      :chart-data="chartData"
      :date="date"
      :unit="$t('件')"
    />
  </v-col>
</template>

<i18n>
{
  "ja": {
    "新型コロナウイルスに関する一般相談件数": "新型コロナウイルスに関する一般相談件数",
    "件": "件"
  }
}
</i18n>

<script>
import formatGraph from '@/utils/formatGraph'
import TimeBarChart from '@/components/TimeBarChart.vue'

export default {
  components: {
    TimeBarChart
  },
  props: {
    date: {
      type: String,
      default: ''
    },
    data: {
      type: Array,
      default: () => []
    }
  },
  computed: {
    chartData() {
      return formatGraph(this.data)
    }
  }
}
</script>
