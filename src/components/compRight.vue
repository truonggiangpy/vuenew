<template>
  <div id="right">
    <CompTop/>
    <CompContent
    v-bind:arrayTemTam="arrayTemTam"
    v-bind:arrayTem="arrayTem"
    v-bind:indexEdit="indexEdit"
    @editLine = "editLine"
    />
  </div>
</template>
<script>
import CompTop from './compRight/compTop'
import CompContent from './compRight/compContent'
export default {
  name: 'right',
  components: {
    CompTop,
    CompContent

  },
  data () {
    return {
      indexEdit: 0,
      arrayTemTam: [],
      arrayTem: [
        // Temlate: this.Temlate,Type: this.Type, Company: this.Company,VersionDate: this.VersionDate, ExpirationDate: this.ExpirationDate, Active: this.Active
        {

          idfrom: '1115',
          Temlate: 'bahaha hihhi ',
          Type: 'Production',
          Company: 'Peptico',
          VersionDate: '17-12-2020',
          ExpirationDate: '17-12-2020',
          Active: 'Active',
          node1: 'Remove',
          node2: 'Edit'
        },
        {
          idfrom: '1113',
          Temlate: 'a3325243-AFM-B6-TV-RADIOCOMMERCIALS-11-15',
          Type: 'Production',
          Company: 'Haitico',
          VersionDate: '20-11-2020',
          ExpirationDate: '20-11-2020',
          Active: 'Archive',
          node1: 'Remove',
          node2: 'Edit'
        },
        {
          idfrom: '1111',
          Temlate: 'huhuhahahahaahahahaah',
          Type: 'Payoll',
          Company: 'Haitico',
          VersionDate: '25-12-2020',
          ExpirationDate: '20-11-2020',
          Active: 'Active',
          node1: 'Remove',
          node2: 'Edit'
        },
        {
          idfrom: '1114',
          Temlate: 'c324-AFM-B6-TV-RADIOCOMMERCIALS-11-15',
          Type: 'Production',
          Company: 'Peptico',
          VersionDate: '20-11-2020',
          ExpirationDate: '20-11-2020',
          Active: 'Active',
          node1: 'Remove',
          node2: 'Edit'
        },
        {
          idfrom: '1112',
          Temlate: '1999-AFM-B6-TV-RADIOCOMMERCIALS-11-15',
          Type: 'Payoll',
          Company: 'Peptico',
          VersionDate: '22-12-2020',
          ExpirationDate: '20-11-2020',
          Active: 'Archive',
          node1: 'Remove',
          node2: 'Edit'
        }
      ]
    }
  },
  created () {
    for (const property in this.arrayTem) {
      this.arrayTemTam.push(this.arrayTem[property])
    }
  },
  methods: {
    editLine (e) {
      let index = 0
      let check = true
      for (let [i, v] of this.arrayTem.entries()) {
        if (String(e.idfrom) === String(v.idfrom)) {
          index = i
        }
        if (v.node2 === 'Cancel_row' || v.node2 === 'Cancel') {
          check = false
        }
      }
      alert(index)
      if (check) {
        this.indexEdit = index
        e.ExpirationDate = this.convertDate(e.ExpirationDate.trim(), '-', 'dd_mm_yyyy')
        e.VersionDate = this.convertDate(e.VersionDate.trim(), '-', 'dd_mm_yyyy')
        this.arrayTem[-2] = this.arrayTem[index]
        this.arrayTem[index].node2 = 'Cancel_row'
        // this.arrayTem.splice(index, 1, e)
        alert(this.arrayTemTam[index].node2)
      }
      this.arrayTem[-2].node2 = 'Edit'
      this.arrayTemtam = []
      // for (const [i] of this.arrayTem.entries()) {
      for (let i = 0; i <= this.arrayTem.length; i++) {
        this.arrayTemTam.push(this.arrayTem[i])
      }
    },
    convertDate: function (date, tt, type) {
      let ngay
      let thang
      let nam
      if (type === 'dd_mm_yyyy') {
        ngay = date.slice(0, 2)
        thang = date.slice(3, 5)
        nam = date.slice(6, 10)
        return nam + tt + thang + tt + ngay
      }
      if (type === 'yyyy_mm_dd') {
        nam = date.slice(0, 4)
        thang = date.slice(5, 7)
        ngay = date.slice(8, 10)
        return ngay + tt + thang + tt + nam
      }
    }
  }
}
</script>
<style scoped>
#right {
  display: flex;
  flex-direction: column;
  flex: 1;
  margin:0px 5px;
  overflow-y: overlay;
}
</style>
