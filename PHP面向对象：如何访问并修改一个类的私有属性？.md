> 类的私有属性不能被直接访问和修改，只能通过自身提供的方法去访问和修改
``` php
class a{
	private $name = 'hello world';
	public $sex = 'man';
	function get(){
		echo $this->name;
	}
	function set(){
		$this->name = 'I love you';
	}
}

class b{
	public $a;
	function __construct(){
		$this->a = new a();
	}

	function say1(){
		echo $this->a->name; //Fatal error: Cannot access private property a::name 
	}
	function say2(){
		echo $this->a->sex; //man
	}
	function say3(){
		$this->a->get();	//hello world
	}
	function say4(){
		$this->a->set();
		$this->a->get();	//I love you
	}
}
```
