### compile 'com.squareup.retrofit2:converter-simplexml:2.1.0'   遇到的问题
* Information:Gradle tasks [:app:assembleDebug, :greendaogenerator:assemble, :test:assemble, :vitamio:assembleDebug]
* Warning:WARNING: Dependency xpp3:xpp3:1.1.3.3 is ignored for debug as it may be conflicting with the internal version provided by Android.
* Warning:WARNING: Dependency xpp3:xpp3:1.1.3.3 is ignored for release as it may be conflicting with the internal version provided by Android.
* Error:trouble processing "javax/xml/XMLConstants.class":
* Error:Ill-advised or mistaken usage of a core class (java.* or javax.*)
* Error:when not building a core library.
* Error:This is often due to inadvertently including a core library file
* Error:in your application's project, when using an IDE (such as
* Error:Eclipse). If you are sure you're not intentionally defining a
* Error:core class, then this is the most likely explanation of what's
* Error:going on.
* Error:However, you might actually be trying to define a class in a core
* Error:namespace, the source of which you may have taken, for example,
* Error:from a non-Android virtual machine project. This will most
* Error:assuredly not work. At a minimum, it jeopardizes the
* Error:compatibility of your app with future versions of the platform.
* Error:It is also often of questionable legality.
* Error:If you really intend to build a core library -- which is only
* Error:appropriate as part of creating a full virtual machine
* Error:distribution, as opposed to compiling an application -- then use
* Error:the "--core-library" option to suppress this error message.
* Error:If you go ahead and use "--core-library" but are in fact
* Error:building an application, then be forewarned that your application
* Error:will still fail to build or run, at some point. Please be
* Error:prepared for angry customers who find, for example, that your
* Error:application ceases to function once they upgrade their operating
* Error:system. You will be to blame for this problem.
* Error:If you are legitimately using some code that happens to be in a
* Error:core package, then the easiest safe alternative you have is to
* Error:repackage that code. That is, move the classes in question into
* Error:your own package namespace. This means that they will never be in
* Error:conflict with core system classes. JarJar is a tool that may help
* Error:you in this endeavor. If you find that you cannot do this, then
* Error:that is an indication that the path you are on will ultimately
* Error:lead to pain, suffering, grief, and lamentation.
* Error:1 error; aborting
* Error:Execution failed for task ':app:transformClassesWithDexForDebug'.
* > com.android.build.api.transform.TransformException: java.lang.RuntimeException: java.lang.RuntimeException: * * com.android.ide.common.process.ProcessException: java.util.concurrent.ExecutionException: java.lang.UnsupportedOperationException
* Information:BUILD FAILED
* Information:Total time: 12.645 secs
* Information:34 errors
* Information:2 warnings
* Information:See complete output in console

### 解决方法
* compile ('com.squareup.retrofit2:converter-simplexml:2.1.0')
*     {
*         exclude module: 'stax-api'
*         exclude module: 'stax'
*         exclude module: 'xpp3'
*     }
* 参考http://stackoverflow.com/questions/35804080/retrofit-2-0-xml-simplexml-converter-issue-while-having-retrolambda-in-gradle-fi
