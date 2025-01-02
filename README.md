# String Calculator TDD Kata

This project demonstrates the implementation of the String Calculator TDD Kata in Ruby, with test-driven development (TDD) principles.

## Prerequisites

Make sure you have the following installed:

- Ruby (>= 3.0.1)
- Bundler

## Setup

1. Clone the repository or download the project files.

   ```bash
   git clone <repository-url>
   cd string_calculator
   ```

2. Install dependencies using Bundler:

   ```bash
   bundle install
   ```

## Running Tests

The project uses RSpec for testing. Run the tests using the following command:

```bash
bundle exec rspec string_calculator_spec.rb
```

## Project Structure

- `string_calculator.rb`: Contains the implementation of the String Calculator.
- `string_calculator_spec.rb`: Contains the RSpec tests for the String Calculator.
- `Gemfile`: Lists the project dependencies.
- `Gemfile.lock`: Tracks the exact versions of gems installed.

## Usage

The `StringCalculator` class has a single method `add` that performs the following:

- Returns `0` for an empty string.
- Adds up comma-separated numbers in a string.
- Supports newlines as delimiters.
- Allows custom delimiters defined in the format `//[delimiter]\n[numbers]`.
- Raises an exception if negative numbers are passed, listing all negative numbers.

### Example

```ruby
require_relative 'string_calculator'

calculator = StringCalculator.new

puts calculator.add("")             # Output: 0
puts calculator.add("1")            # Output: 1
puts calculator.add("1,2")          # Output: 3
puts calculator.add("1\n2,3")       # Output: 6
puts calculator.add("//;\n1;2;3")   # Output: 6

begin
  calculator.add("1,-2,-3")
rescue => e
  puts e.message                     # Output: negative numbers not allowed -2, -3
end
```

## License

This project is open-source and available under the MIT License.