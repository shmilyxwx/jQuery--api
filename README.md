			window.jQuery = function (nodeOrSelector){
				let node = {}
				if(typeof nodeOrSelector === 'string'){
					node = document.querySelectorAll(nodeOrSelector)
				}else{
					node = nodeOrSelector
				}
				return{
					addClass: function(classes){
						for(let i =0 ;i<node.length;i++){
							node[i].classList.add(classes)
						}
					},
					setText: function(str){
						for(let i=0 ;i<node.length;i++){
							node[i].textContent = str
						}
					}
				}
			}
			window.$ = jQuery
			var div1 = document.getElementsByTagName("div")
			var $div = $(div1)
			$div.addClass('red')
			$div.setText('hi')
			
			
			
```			
1.首先声明一个全局jQuery变量
2.让其值为一个匿名函数
3.在这个函数中声明一个node变量,这个函数接受一个参数并且返回一个对象
4.首先判断传入这个参数值的类型
5.如果传入的是字符串得到所有的对象然后通过document.querySelectorAll获取到传入值的全部节点对象
否则node的值为传入的伪数组对象
6.返回的对象中有两个函数体,分别为addClass与setText,做相应的操作得到想要的结果
```