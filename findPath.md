class Obj {
  constructor() {
    this.data = {
      a: {
        b: {
          c: 12
        }
      }
    };
  }

  findPath = (str) => {
    let sol = this.data;
    for (let key of str.split(".")) {
      sol = sol[key];
      if (!sol) {
        return undefined;
      }
    }
    return JSON.stringify(sol);
  };
}

let obj = new Obj();






console.log(obj.findPath('a.b.c')); // 12
console.log(obj.findPath('a.b')); // {c: 12}
console.log(obj.findPath('a.b.d')); // undefined
console.log(obj.findPath('a.c')); // undefined
console.log(obj.findPath('a.b.c.d')); // undefined
console.log(obj.findPath('a.b.c.d.e')); // undefined
