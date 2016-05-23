# Niall Questions

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
