<script setup lang="ts">
import * as XLSX from "xlsx"
import * as jsontoxml from "jsontoxml"

// Read the file
function logSheet() {
    const workbook = XLSX.readFile("a.xlsx")
    let worksheets = {}
    for (const sheetName of workbook.SheetNames) {
        worksheets[sheetName] = XLSX.utils.sheet_to_json(workbook.Sheets[sheetName])
    }
    console.log(worksheets)
}

</script>

<template>
    <button @click="logSheet()">Generate</button>
</template>
