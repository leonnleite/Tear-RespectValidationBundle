Tear\RespectValidationBundle
============================
better integration between Symfony2 and "The most awesome validation engine ever created for PHP." 



Installation
============

##Bring in the vendor libraries


Use Composer 

    // composer.json
    "require": {
        "php": ">=5.3.2",
        // ...
        "tear/respect-validation-bundle": "dev-master",
        // ...
    }



##Add to your application kernel

    // app/AppKernel.php
    public function registerBundles()
    {
        return array(
            // ...            
            new Tear\Respect\ValidationBundle\TearRespectValidationBundle(),
            // ...
        );
    }




************

Usage
=====

### Use as service respect.validator:
    
        //...
        class AcmeController extends Controller
        {
            public function indexAction()
            {
                $number = 123;
                $x = $this->get('respect.validator')->numeric()->validate($number);//true
        //...


### Use as Alias:

    
        <?php
        
        namespace Acme\DemoBundle\Controller;
        
        use Symfony\Bundle\FrameworkBundle\Controller\Controller;
        use Respect\Validation\Validator as v;
        class AcmeController extends Controller
        {
            
            public function indexAction()
            {
        
                $validUsername = v::alnum()
                ->noWhitespace()
                ->length(1,15);
                
                $x = $validUsername->validate('alganet'); //true
                //...

        
## Documentation
        
See documentation on https://github.com/Respect/Validation
  
