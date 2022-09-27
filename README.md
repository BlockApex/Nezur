# Nezur
Nezur written in Rust designed for fuzzing/property-testing of NEAR smart contracts. It uses advanced fuzzing mechanism based on wasm grammer to negate user-defined predicates. It is highly modular and can be extend to include sophisticated evolutionary fuzzing techniques.

### Milestone breakdown
 - Generate Input/Calldata Generation
      + Leverage both smart contracts & .wasm files to generate call data.
      + Mock context generation with near-runtime
        + Option to forking state trie & account impersonation { For testing over underlying deployed app }
  + Parametric fuzzing & Property Testing using assertions
      + Designing cheatcodes
        + Environmental
        + Assertion
        + Fuzzer assume
        + Utilities
  + Sequence of transaction fuzzing along with coverage guided fuzzing with optional state pruning
      + SetUp function for fuzz configuration
      + Devise algorithm to generate initial sequence
      + Devise algorithm for state pruning using intelligent node selection
  + Symbolic Constraint identification
      + Generate & store logical equation that would be solved using a z3 solver which can be used by corpus to advance with fuzzing campaign
  + Automatic testcase minimization for quick triage
    + Code Coverage for fuzzing campaigns
      + Coverage report in % of lines covered (html)
  + Optional Corpus Generation
  + Corpus replay for failed fuzz cases
  + Seamless integration into development workflow (CI/CD)
  + Performace evalation
