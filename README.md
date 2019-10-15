# cacher is a definition with cache

you can use `Register(Cacher)` in your init to implements a `Cacher` then use the interface{}
```go
/*Cacher define an cache interface */
type Cacher interface {
	//get a value
	Get(key string) (interface{}, error)
	//get a value from cache with default
	GetD(key string, v interface{}) (interface{}, error)
	//set a value to cache
	Set(key string, val interface{}) (Cacher, error)
	//set a value with ttl
	SetWithTTL(key string, val interface{}, ttl int64) (Cacher, error)
	//check the value is exist
	Has(key string) (bool, error)
	//delete a value
	Delete(key string) (Cacher, error)
	//clear all the values
	Clear() error
	//get multi values
	GetMultiple(keys ...string) (map[string]interface{}, error)
	//set multi values with [key]value
	SetMultiple(values map[string]interface{}) (Cacher, error)
	//delete multi values
	DeleteMultiple(keys ...string) (Cacher, error)
}
```
