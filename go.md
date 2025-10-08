```go 
package main

import (
    "bytes"
    "fmt"
    "io/ioutil"
)

func main() {
    jsonData := []byte(`{"username":"yehia"}`)

    // نحط البيانات داخل Buffer
    buf := bytes.NewBuffer(jsonData)

    // نقرأ منها أول مرة
    first, _ := ioutil.ReadAll(buf)
    fmt.Println("القراءة الأولى:", string(first))

    // نحاول نقرأ تاني
    second, _ := ioutil.ReadAll(buf)
    fmt.Println("القراءة الثانية:", string(second))
}


النتيجة:


القراءة الأولى: {"username":"yehia"}
القراءة الثانية: 
يعني:
✅ أول مرة قرينا البيانات كلها.
❌ المرة التانية طلعت فاضية لأن البافر اتقرأ خلاص — المؤشر جرى للنهاية.
