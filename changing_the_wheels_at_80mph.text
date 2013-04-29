Overview
- You can dual boot rails 2 and rails 3
- Let's tak about numbers
  - Rails version vs number of servers
  - Lots of people still on rails 2
  - Very hard to migrate away: takes time, lots of risk

- Upgrading to rails 3
  1. Procrastinate
  2. Goals
  3. Onto master
     1. Boot rails 3
     2. Dual boot
     3. Unbreak rails 2
     4. Merge upstream
  4. Getting it to work
  5. Rollout
  6. Lessons learned

- Stupid Things We Tried (upgrading to 1.9)
  - Putting it off
  - Rearchitecting the app first
  - Do it all in a big spike!
  - Have a ruby_19 branch

- Rails 3, why now?
  - burke/zues (benefits to rails 3)
  - Security
  - More expensive to stay on rails 2 than to move away

- Don't break the world
- Keep everyone happy
- Keep ourselves happy

- rails/rails_upgrade
- bundler
  - platforms directive for ruby 1.8 vs ruby 1.9
  - monkey-patched
    - two Gemfile.lock files (Gemfile then contains `if is_rails3; blah; else; other-blah`)
    - export USE_RAILS_3=true
    - feature lock the framework

- Make it easy for everyone
  - # script/server3

- Have tests you trust
- Use CI

- Punt when you can
  - Silenced deprications
  - Old routes still work
  - Old mailers still work
  - self.store_full_sti_class = false (for models that rely on old STImethod)
  - old views (can) still work (probably not relevant to doa)
  - your error handling (can) still work (also probably not relevant)
  - temporarily ugly

- Extensive manual testing
- Make everyone a tester
- Turn on Rails 3 by default

- Rails 2 and Rails 3 sessions are completely incompatible
  - envato/rails_4_session_flash_backport

- Pause the world (no other deployments)
- A few very tiny fires
  - acts_as_auditable (lost track of who changed it)
  - punching activescaffold in the face

- Lots of cleanup

- Lessons learned
  - preorder the donuts your on-call engineers like
  - deprecate activescaffold
    - just because it works, doesn't mean it's going to work -- if you're not using it, get rid of it
  - schedule lots of time for firefighting and cleanup

- Get everything into master as early as possible
- CI is your best friend

newrelic.com/rails3_upgrade