require_relative 'config/environment.rb'
require "sinatra/activerecord/rake"

desc "starts console"
task :console do
  Pry.start
end


namespace :db do
  desc "Erase all tables"
  task :clear => :environment do
    conn = ActiveRecord::Base.connection
    tables = conn.tables
    tables.each do |table|
      puts "Deleting #{table}"
      conn.drop_table(table)
    end
  end
end
