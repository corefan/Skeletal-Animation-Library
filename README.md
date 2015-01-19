# Skeletal-Animation-Example

A small C++14 library that draws skeletal animation models given animation number and time. Made to be used with other libraries such as Bullet Physics and Box2D. 

### Features

* Simple way to draw unanimated models (using model.hpp)
* Simple way to calculate and draw animation frames from skeletal animation models (using skeletal_animation_model.hpp)

### TODO

* Draw using newer OpenGL with skinning on GPU instead of CPU (see SkeletalAnimationModel::drawMeshFrame(const MeshType&)

###Usage

See sfml_examples.cpp

###Dependencies

sfml_examples.cpp uses SFML (http://www.sfml-dev.org/), and the header-files are dependent on Assimp (http://assimp.sourceforge.net/) and OpenGL. 

Additionally, the library is using C++14 features. 

### Compile and run

Use cmake and make to compile. 

Then, to run the examples: ./sfml_examples
