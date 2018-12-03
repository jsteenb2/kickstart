# Readis - Build me a Redis Clone

We're gonna stretch those go muscles out a bit here. Readis will test your working knowledge of key Go paradigms. We'll touch on:

* Value vs Pointer semantics
* Decoupling via interfaces
* Testing
* Dependency Injection
* Std libs io, os, time, encode/json, fmt and more 

## Day 1

Create Readis, a redis clone(k/v store) that provides the following:

- [ ] Constructor for Readis type
- [ ] Set method that takes id, data in the form of interface{}, and expiration time in time.Duration and returns an error
    - Set method encodes data with json.Marshal
- [ ] Get method for reading by id, returns ([]byte, error)
- [ ] Expire keys after expiration time has lapsed (can be done on read), return no results from store if it has expired
- [ ] Create executable that will set/get entries

## Day 2

Extend Readis to provide the following:

- [ ] Validate that expiration time is greater than 100ms on Set call
- [ ] Make Encoder configurable on Readis type 
- [ ] Export method to write to an io.Writer (file, os.StdOut, etc...) and return an error if seen

## Day 3

Extend Readis to be provide concurrent access:

- [ ] Calls to Set are serialized
- [ ] Reads can be called without blocking
- [ ] Exporting locks the dataset while processing the export
- [ ] Expiration is done on a rolling basis (when time to expire happens will drop k/v from dataset)
