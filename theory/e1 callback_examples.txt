callback_examples.rb ::  


First Example :: 


class Listing < ApplicationRecord
  after_create :set_expiry_date

  private

  def set_expiry_date
    expiry_date = Date.today + 30.days
    self.update_column(:expires_on, expiry_date)
  end
end




three basic types of Callback ::  

before_create – Runs the method before the stated action
after_create – Runs the method after the stated action
around_create – A bit trickier. In this one, you will write a method which actually yields at some point to the original action. That way you can have code before it and after it and YOU decide at which point the original action gets done. Not entirely common.



Example of before and after create in callbacks :: 

# app/models/user.rb
  class User < ActiveRecord::Base

    before_create do |user|
      puts "about to create #{user.name}"
    end

    after_create :just_created

    private

    def just_created
      puts "just created a user"
    end
  end


  