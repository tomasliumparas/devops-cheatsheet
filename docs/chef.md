## Show node attributes
```
knife node show $(hostname) -c /etc/chef/client.rb --medium
```

## Edit node attributes
```
export EDITOR=vi
knife node edit $(hostname) -c /etc/chef/client.rb
```
