# SimpleDependencyContainerUnity
Simple Dependency Injection Container for Unity projects

## Features
- Can create instances of classes and inject dependencies via constructor.

    ```Container.Resolve<MyType>();
    
    class MyType(ISomeDependency dep) {}

- Can pass dependencies to fields and properties.

    ```[Dependency(typeof(MyInterfaceType))]
    MyInterfaceType m_SomeObject;
    
    ..
    
    Container.InjectDependenciesInto(objectWhichHaveThisField)
    
- Can register Singletons as dependencies

    `[RegisterDependency(typeof(MyInterfaceType), true)]`
    
- Includes *DependencyContainerBehaviour* which can register referenced GameObjects as singleton dependencies. This behaviour on awake will automatically pass dependencies to all gameobject components in current scene.

## Bes Practices

It is best to have all controllers/manager classes in once scene, map itself in a different scene. Put DependecyContainerBehaviour in the controller scene.
  
  
