# hello world

hello world入门
----
* cd easyswoole_demo
* cd App/HttpController
* vim Demo.php
        

    <?php
    /**
     * Demo.php
     * Created by PhpStorm.
     * User: yanxiaowei
     * Date: 2018/5/30
     * Time: 11:25
     */
    namespace App\HttpController;
    
    use EasySwoole\Core\Http\AbstractInterface\Controller;
    
    class Demo extends Controller {
    
        public function index() {
    
        }
    
        public function hello() {
            $this->response()->write("hello world!");
        }
    }
* 验证，浏览器访问: http://127.0.0.1:9501/demo/hello
* 结果：显示"hello world"