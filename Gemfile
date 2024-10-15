source "https://rubygems.org"

gemspec

is_unix = RUBY_PLATFORM =~ /(aix|darwin|linux|(net|free|open)bsd|cygwin|solaris|irix|hpux)/i
is_truffleruby = RUBY_DESCRIPTION =~ /truffleruby/
is_win = RUBY_PLATFORM =~ /(mswin|msys|mingw|cygwin|bccwin|wince|emc)/i

if is_unix && ENV['WITH_VTERM']
  gem "vterm", github: "ruby/vterm-gem"
  gem "yamatanooroti", github: "ruby/yamatanooroti"
end
if is_win
  gem "yamatanooroti", github: "yo4/yamatanooroti", branch: "ci_for_windows"
end

gem "stackprof" if is_unix && !is_truffleruby

gem "reline", github: "YO4/reline", branch: "windows_fix" if ENV["WITH_LATEST_RELINE"] == "true"
gem "rake"
gem "test-unit"
gem "test-unit-ruby-core"

gem "rubocop"

gem "tracer" if !is_truffleruby
gem "debug", github: "ruby/debug", platforms: [:mri, :mswin]

if RUBY_VERSION >= "3.0.0" && !is_truffleruby
  gem "repl_type_completor"
end
