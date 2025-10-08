```go 
package main

import (
    "fmt"
    "io/ioutil"
    "net/http"
)

func main() {
    url := "https://api.example.com/v1/users" // <-- غيره حسب API الحقيقي
    apiKey := "YOUR_API_KEY_HERE"

    // نعمل request جديد من النوع GET
    req, err := http.NewRequest("GET", url, nil)
    if err != nil {
        fmt.Println("Error creating request:", err)
        return
    }

    // نضيف الـ API key داخل الـ Header
    req.Header.Add("Authorization", "Bearer "+apiKey)
    req.Header.Add("Accept", "application/json")

    // نستخدم client علشان ننفذ الطلب
    client := &http.Client{}
    resp, err := client.Do(req)
    if err != nil {
        fmt.Println("Error sending request:", err)
        return
    }
    defer resp.Body.Close()

    // نقرأ الرد
    body, _ := ioutil.ReadAll(resp.Body)

    fmt.Println("Status:", resp.Status)
    fmt.Println("Response:", string(body))
}

