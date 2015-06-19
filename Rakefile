# Define new tasks below
task :environment do
  require_relative './config/environment'
end

desc "Loads an interactive console."
task :console => [:environment] do
  load './bin/console'
  exit
end

# This is an example of a Rake Task called "hello_rake"
task :hello_rake do
  puts "Hello, from rake"
end

task :default do
  puts "Hello, from default task!"
end

task :upcoming_todos => [:environment] do
  User.with_upcoming_todos.each do |user|
    puts "Emailing #{user}"
  end
end

#namespacing a task
namespace :todos do
  task :mark_overdue => [:environment] do
    Todo.mark_overdue
  end
  task :mark_upcoming => [:environment] do
    Todo.mark_upcoming
  end
end


task :overdue_todos => [:environment] do
  User.with_overdue_todos
  puts "Emailing A User"
end




namespace :user do
  desc "Send a summary to a User"
  task :send_summary, [:email] => [:environment] do |t, args|
    # [email] is the argument array
    # [environment] is the prerequisite task array
    puts "Sending summary to user with #{args[:email]}"
  end
end