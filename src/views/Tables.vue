<template>
  <title-bar :title-stack="titleStack" />
  <div class="px-5 py-3 text-3xl">Tables</div>
  <main-section>
    <card-component class="mb-6" title="Clients" :icon="mdiAccountMultiple" has-table>
      <clients-table checkable/>
    </card-component>

    <title-sub-bar :icon="mdiTableBorder" title="Wrapped variation"/>

    <card-component class="mb-6" has-table>
      <clients-table checkable/>
    </card-component>

    <title-sub-bar :icon="mdiTableOff" title="Empty variation"/>

    <notification color="danger" :icon="mdiTableOff">
      <b>Empty table.</b> When there's nothing to show
    </notification>
    <card-component empty/>
  </main-section>

</template>

<script>
import { ref } from 'vue'
import { mdiMonitorCellphone, mdiAccountMultiple, mdiTableBorder, mdiTableOff } from '@mdi/js'
import MainSection from '@/components/MainSection'
import Notification from '@/components/Notification'
import ClientsTable from '@/components/ClientsTable'
import CardComponent from '@/components/CardComponent'
import TitleBar from '@/components/TitleBar'
import TitleSubBar from '@/components/TitleSubBar'

export default {
  name: 'Tables',
  components: {
    TitleSubBar,
    MainSection,
    TitleBar,
    CardComponent,
    ClientsTable,
    Notification
  },
  setup () {
    const titleStack = ref(['Admin', 'Tables'])

    return {
      titleStack,
      mdiMonitorCellphone,
      mdiAccountMultiple,
      mdiTableBorder,
      mdiTableOff
    }
  }
}
</script>
