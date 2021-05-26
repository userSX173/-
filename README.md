# -
        在js之中的原型链的自我理解
        
        所有函数对象的隐原型都指向Function的显原型；
        所有原型对象的隐原型都指向Object的显原型；
        所有普通对象的隐原型都指向他的构建函数的显原型；
        Function 和 Object是特殊的俩大类
        实例中没有constructor ，所以在查找实例的constructor会沿着隐原型查找，也就是查找构造函数的原型对象
        constructor指向构造函数的原型，原型的constructor指向构造函数
        函数的组合继承中没有更改隐原型而是切换了显原型，沿着隐原型查找的过程中发生了改变 所以会发生constructor指向更改的情况//eg Son.prototype = new Father();   console.dir(Son.__proto__)           指向Function;
        在类继承中则相左
        子类继承父类时子类的隐原型指向了父类自身 //eg class Son extends Father  console.dir(Son.__proto__) //指向了Father;
        constructor是显原型中的，所以函数会改变constructor，而类则不会。
