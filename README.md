
new Promise(resolve => {
    console.log("加油，继续努力!");
    setTimeout(() => {
        resolve("100")
    }, 1000)
}).then( value => {
    return new Promise(resolve => {
        console.log("马上成功了!");
        setTimeout(() => {
            resolve("200")
        }, 1000)
    }).then( val => {
        return new Promise( reject => {
            console.log("失败了!");
            setTimeout(() => {
                reject("300")
            }, 1000)
        }).catch( error => {
            console.log("error: ", error);
        });
    })
})
