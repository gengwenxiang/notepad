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