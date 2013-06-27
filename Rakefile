#!/usr/bin/env rake

def default_blog_template()
  File.read('_templates/default_post.txt')
end

POST_TEMPLATE = default_blog_template()

namespace :blog do

  desc "Create a new blog post with a custom title"
  task :new, [:title] do |t, params|

    raise "\n[ERROR] You need an author.yml file, try: cp author.yml{.example,} and then run me again" unless File.exists?('author.yml')
    author = YAML.load(File.read('author.yml'))

    # strip the string
    title = params.title.downcase.strip

    # blow away apostrophes
    title.gsub! /['`]/,""

    # @ --> at, and & --> and
    title.gsub! /\s*@\s*/, " at "
    title.gsub! /\s*&\s*/, " and "

    # replace all non alphanumeric, underscore or periods with underscore
    title.gsub! /\s*[^A-Za-z0-9\.\-]\s*/, '-'

    # convert double underscores to single
    title.gsub! /-+/,"-"

    # strip off leading/trailing underscore
    title.gsub! /\A[-\.]+|[-\.]+\z/,""

    # now add the time to the string
    title.insert 0, Time.now.strftime("%Y-%m-%d-")

    # add the file extension
    title.insert -1, '.md'

    rendered_post = POST_TEMPLATE.gsub /{{(title|name|github|twitter|email)}}/, "{{title}}" => params.title, "{{name}}" => author['name'], "{{github}}" => author['github'], "{{twitter}}" => author['twitter'], "{{email}}" => author['email']

    #create the file
    File.open('_posts/' + title, 'w') {|f| f.write(rendered_post) }

    puts "Created " + title

  end
end

def git_clean?
  git_state = `git status 2> /dev/null | tail -n1`
  clean = (git_state =~ /working directory clean/)
end

task :check_git do
  unless git_clean?
    puts "Dirty repo - commit or discard your changes and run deploy again"
    exit 1
  end
end

desc "Deploy to remote origin"
task :deploy => [:check_git] do
  source_branch = 'source'
  deploy_branch = 'master'
  message = "Site updated at #{Time.now.utc}"

  system "bundle exec jekyll build"
  system "git checkout \"#{deploy_branch}\""
  system "cp -r _site/* . && rm -rf _site/ && touch .nojekyll"

  unless git_clean?
    system "git add . && git commit -m \"#{message}\""
    system "git push origin \"#{deploy_branch}\""
    puts "Pushed to origin and pages with commit message: #{message}"
  else
    puts "No changes to deploy - canceled"
  end

  system "git checkout \"#{source_branch}\""
end