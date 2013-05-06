Describing Your World With Seahorse
@trevorrowe

- Amazon Web Services
  - gem install aws-sdk
  - npm install aws-sdk

- Open source can be rewarding and challenging
  - Chaotic, like herding cats

- Let's Talk about APIs
  - Web-service APIs
  - AWS is a strong proponent of building services

- Breaking apart the MonoRail
- Rails as an API platform (official unintentional theme of railsconf 2013)

- APIs should be Entities (not side-effects)

- Models, Views, Controllers, Oh My!
  - Models are doing too much (cramming in more than just basic business logic)
  - Models are taking on too much responsibility
  - The shape of your API should be driven by your Domain model, not your persistence model

- Why do you "Need" an API Model
  - Filter incoming parameters
  - Perform parameter type conversion
  - Generate comprehensive API documentation
  - Generate clients
  - Version

- Describing your world with seahorse
  - Seahorse describes the "shape" of a web service API
  - It does not describe the protocol
  - Extracted from our work on building AWS clients in multiple languages
    - PHP, Python, JavaScript, Ruby

- awslabs/seahorse (gem install seahorse)

- Q: What does Rails provide to help me build API models
  - A: Not much

- Whitelisted Attributes
  - Not type aware
  - Doesn't support multiple configurations
  - Ugle to use with nested_attributes_for

- Rails 4 To the Rescue!
  - Strong parameters

- Strong Paramters
  - Issues
  - Weak parameters

- Seahorse Types
  - Complex Types
  - Scalar Types
  - Type Metadata

