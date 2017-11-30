# Tool-library
工具库（一些常用的方法总结）


// 完全分辨每一个传进去的东西
// 1.分两类 ： 原始值   引用值
// 2.区分引用值
function type(target) {
    var typeStr = typeof(target),
    toStr = Object.prototype.toString,
    objStr = {
        "[object Object]" : "object - Object",
        "[object Array]" : "array - Object",
        "[object Number]" : "number - Object",
        "[object Boolean]" : "boolean - Object",
        "[object String]" : "string - Object"
    }
    if(target === null) {
        return null;
    }else if(typeStr === "function") {
        return "function";
    }
    if(typeStr !== "object") {
        return typeStr;
    }else{
        return objStr[toStr.call(target)];
    }
}
