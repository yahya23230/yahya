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

css
Copy code
القراءة الأولى: {"username":"yehia"}
القراءة الثانية: 
