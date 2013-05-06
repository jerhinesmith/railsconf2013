The Magic Tricks of Testing
@sandimetz

https://speakerdeck.com/skmetz/magic-tricks-of-testing-railsconf

- What percent of the code that you see is tested?

- I hate my tests
  - Why?
    - They're slow
    - They're fragile
    - They're expensive
    - They are misery incarnate

- It doesn't have to be this way
- Just delete some tests

- Unit Tests: Goals
  - Thorough
  - Stable
  - Fast
  - Few

- How does your app feel?
  - Messy

- Focus on messages
- Objects are simple-minded

- Object Under Test
  - Receive messages from others (incoming)
  - Sent messages to others (outgoing)
  - Sent to self

- Message Origin
  - Incoming
  - Sent to self
  - Outgoing

- Message Type
  - Query
    - Return something/change nothing
  - Command
    - Return nothing/change something

- We conflate commands and queries at our peril, but we do it all the time

- Message Origin x Type
-------------------------------------------------------------------
              | Query         |  Command                          |
-------------------------------------------------------------------
Incoming      | Asert result  | Assert direct public side effects |
-------------------------------------------------------------------
Sent to Self  | Ignore                                            |
-------------------------------------------------------------------
Outgoing      | Ignore        | Expect to send                    |
-------------------------------------------------------------------

- Rule
  - Test incoming query messages by making assertions about what they send back

- Test the interface, not the implementation (incoming query messagse)

- Rule
  - Test incoming command messages by making assertions about side effects

- Dry it Out

- Sent to Self
  - Anti-pattern
  - Redundant
  - Do not test, do not make assertions about their values
  - Caveat: Break rule if it saves $$$ during development

- Outgoing Query
  - Anti-pattern
  - Redundant
  - Duplicates other model's tests
  - Do not test them, do not make assertions about their result, do not expect to send them

- If a message has no visible side-effects
  - the esender should not test it

- Outgoing Command
  - Use mocks, and set expectations on the message being sent
  - Expect to send outgoing command messages
  - Caveat: Break rule if side effects are stable and cheap

- But!
- Pain
- API Drift

- Rule
  - Honor the contract
  - Ensure test doubles stay in sync with the API

- Automagically
  - psycho/bogus
  - benmoss/quacky
  - xaviershay/rspec-fire
  - cfcosta/minitest-firemock

- Summary
  - be a minimalist
  - use good judgement
  - test everything once
  - test the interface
  - trust collaborators
  - insist on simplicity
  - practice the tricks