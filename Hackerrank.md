# Plus Minus
```
function plusMinus(arr) {
    // Write your code here

    let divisor = arr.length
    let zero = 0
    let negative = 0
    let positive = 0
    for(let i=0; i< arr.length; i++){
        if(arr[i]>0){
            positive++
        }
        else if(arr[i]<0){
            negative++
        }
        else{
            zero++
        }
        }
        console.log((positive/divisor).toFixed(6) + "\n" + (negative/divisor).toFixed(6) + "\n" + (zero/divisor).toFixed(6) )
}

```
# Min Max Sum

```
function miniMaxSum(arr) {
    // Write your code here
    let new_arr = arr.slice(0)
    let sorted = new_arr.sort((a, b) => a - b );
    let sum = 0
    for(let i=0; i< sorted.length; i++){
        sum += sorted[i]
    }
    console.log(sum-sorted[4], sum-sorted[0])
   
}
```

# Time Conversion
```
function timeConversion(s) {
    // Write your code here
    let time = s.slice(0,8)
    let hour = s.slice(0,2)
    let daytime = s.slice(8,10)
    
    if(daytime === 'AM'){
        if(hour==='12'){
            let new_time = "00"+ s.slice(2,8)
             return new_time
        }
        return time
    }
    else if (daytime === 'PM'){
        if(hour==='12'){
            return time
        }
        else{
            let new_time = (parseInt(hour) + 12).toString() + s.slice(2,8)
             return new_time
        }
       
    }

}
```
