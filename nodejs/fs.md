#### File System (文件系统管理)
1. require('fs')  引入文件系统管理
~~~nodejs
const fs = require('fs')
~~~

#### fs 创建/写入文件
writeFile 异步写入文件
writeFileSync 同步写入文件
- 文件不存在 → 自动创建
- 文件已存在 → 直接覆盖全部内容（无警告）
- file: PathOrFileDescriptor,
- data: string | NodeJS.ArrayBufferView,
- options: WriteFileOptions,
- callback: NoParamCallback,
~~~nodejs
const fs = require('fs')
try {
    fs.writeFileSync('./workspace/text.txt',
        '山不在高，有仙则灵\n')
    console.log('同步写入成功')
} catch (err) {
    console.log('同步写入失败')
}

fs.writeFile('./workspace/text.txt', '水不在深，有龙则灵', {
    flag: 'a',
}, err => {
    if (err) {
        console.log('写入失败')
        return
    }
    console.log('写入成功')
})
~~~

#### fs 追加内容
appendFile  
appendFileSync  
~~~nodejs
try {
    fs.appendFileSync('./workspace/text.txt', '斯是陋室\n')
    console.log('同步插入成功')
} catch (err) {
    console.log('同步插入失败')
}
fs.appendFile('./workspace/text.txt', '唯吾德馨', err => {
    if (err) {
        console.log('插入失败')
        return
    }
    console.log('插入成功')
})
~~~


#### 读取xlsx json
~~~nodejs
const fs = require('fs')
const XLSX = require('xlsx')

// 二进制读取xlsx，不传编码，返回Buffer
fs.readFile('./workspace/src/excel.xlsx', (err, buf) => {
    if (err) {
        console.error('读取失败：', err)
        return
    }
    // 转成json数组
    const workbook = XLSX.read(buf)
    const sheet = workbook.Sheets[workbook.SheetNames[0]]
    // 转成json数组
    const data = XLSX.utils.sheet_to_json(sheet)
    console.log('表格数据', data)
})


fs.readFile('./workspace/package.json', 'utf-8', (err, buf) => {
    if (err) {
        console.log('读取失败', err)
        return
    }

    const data = JSON.parse(buf)
    console.log('data', data)
})
~~~