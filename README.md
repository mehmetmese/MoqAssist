<h1 align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/29013117/107876653-41bf9d00-6ed8-11eb-90b0-770dccce5964.png" width="200"></a>
</h1>

<h4 align="center">A Lightweight Mocking Assistant for Moq Library in .NET Platforms!</h4>


<p align="center">
  <a href="#">
    <img src="https://img.shields.io/badge/dotnet-core5.0-brightgreen">
  </a>
  
  <a href="#">
    <img src="https://img.shields.io/badge/library-Moq-blue">
  </a>
  
  <a href="https://github.com/omeerkorkmazz/MoqAssist/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/Naereen/StrapDown.js.svg">
  </a> 
  
  <a href="https://github.com/omeerkorkmazz/MoqAssist/stargazers/">
    <img src="https://img.shields.io/github/stars/omeerkorkmazz/MoqAssist.svg?style=social&label=Star&maxAge=2592000">
  </a> 
</p>

<p align="center"> 
  <a href="#">
    <img src="https://forthebadge.com/images/badges/made-with-c-sharp.svg">
  </a>
  
  <a href="https://github.com/omeerkorkmazz">
    <img src="https://forthebadge.com/images/badges/powered-by-black-magic.svg">
  </a>  
</p>


<p align="center">
  <a href="#about">About</a> •
  <a href="#sample">Sample</a> •
  <a href="#technologies">Techonologies</a> •
  <a href="#contribution">Contribution</a> •
  <a href="#authors">Authors</a> •
  <a href="#license">License</a> 
</p>

## About
**MoqAssist** is a lightweight and simple mocking assistant used by developers writing unit tests in **.NET platforms** with **Moq** library. Basically, the main purpose is to provide developers to write tests more easily and quickly without fighting with details.

What MoqAssist does is that once registering objects (e.g., dependencies or candidate classes for testing) into the dictionary managed by **MoqAssistDictionary**, MoqAssist automatically builds the constructors of classes by using its dictionary that includes the mocking objects so that a developer does not have to manage the dependencies.

The use of MoqAssist is straightforward as explained in the following;
* Register the objects wanted to be tested only once via *MoqAssistDictionary*.
* Call MoqAssist defining which class will be tested.
* Ready for testing!

## Sample

 * Firstly, create a unit test project. It might be any unit test framework of .NET platforms. In the examples of MoqAssist, xUnit was used.
 * Then, create a class inherited from MoqAssistDictionary to register the mocked objects.
 * Override the *RegisterMocks()* method.

```csharp
namespace MoqAssist.UnitTests.Tests.MockDictionary
{
    public class DefaultMockDictionary : MoqAssistDictionary
    {
        public override void RegisterMocks()
        {
            Register<IUserService>(new Mock<IUserService>());
            Register<ICategoryService>(new Mock<ICategoryService>());
        }
    }
}
```

* *DefaultMockDictionary* will be the once produced class with the registrations of the mocked objects.

```csharp
Register<T>(Mock<T> obj);
```
* Register method is used to store the mocked object into the dictionary.

```csharp
bool IsMockExist<T>();
KeyValuePair<string, object> GetMockPair<T>();
```
* In addition, MoqAssistDictionary offers a couple of methods for searching and validation. 
* For the *Key-Value Pairs*, the key represents the full name of the object and the value represents the mocked object.


## Technologies

* [Dotnet Core](https://dotnet.microsoft.com/) - version net5.0 - Used to implement MoqAssist and MoqAssistDictionary
* [Moq](https://www.nuget.org/packages/Moq/) - version 4.16.0 - Used for mocking business logics.
* [xUnit](https://xunit.net/) - version net5.0 - Used for sample tests.


## Contribution
Feel free to contact me for any questions, discussions, or ideas. [Send Email](mailto:omer.korkmaz.95@windowslive.com?subject=[GitHub]%20MoqAssist)

**How to contribute**
* Fork the repository
* Create a feature branch
* Commit the changes and push the branch
* Create a new pull request


## Authors

* [**Omer KORKMAZ**](https://www.linkedin.com/in/omerkorkmazz/) - *[*@omeerkorkmazz*](https://www.github.com/omeerkorkmazz)*


## License

Distributed under the MIT License. See [LICENSE](https://github.com/omeerkorkmazz/MoqAssist/blob/master/LICENSE) for more information.
