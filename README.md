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