# Niall Questions

## Question 3 29/05/2016

I have a question about database designing.

When storing a phone number, should I store it as a string or as an integer?

When I stored it as an integer i.e. `0405463904` etc, i noticed that the data was stored in the database as `405436904`, dropping the initial `0`.

Considering I'm not likely to be doing any calculations on user phone numbers, should I just store as a string and move on!?

Thanks guys!
-Niall

## Question 2 24/05/2016

Here is code from yesterdays lesson:

```
rails g controller cat index create new edit show update destroy
```

could we have run this on the **home** index too at the beginning?

```
rails g controller home index create new edit show update destroy
```


## Question 1 19/05/2016

Here is code from yesterdays lesson:

### app.erb
```
get '/:subreddit' do
	@title = "Home"
	@links = ["Home", "About", "Links", "Contact", "My Work"]
	if params[:after]
		@reddit_data = HTTParty.get "http://reddit.com/r/#{params[:subreddit]}.json?limit=10&after=#{params[:after]}"
	elsif params[:before]
		@reddit_data = HTTParty.get "http://reddit.com/r/#{params[:subreddit]}.json?limit=10&before=#{params[:before]}"
	else
		@reddit_data = HTTParty.get "http://reddit.com/r/#{params[:subreddit]}.json?limit=10"
	end

	erb :index #render the index file components and render it.
end

```
**My Question**

- Where does `params` come from? When we run the if statement and check `if params[:after]`, how does the computer/server know where to look for `params`? Is this a Reddit specific thing?

Thanks.
