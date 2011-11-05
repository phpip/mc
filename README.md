# mc.go: A pure Go driver for Memcached (binary protocol, thread-safe)

## Install

		$ goinstall github.com/bmizerany/mc.go

## Use

		import "github.com/bmizerany/mc.go"

		func main() {
			// Error handling omitted for demo
			cn, _ := mc.Dial("localhost:11211")
			cn.Set("foo", "bar", 0, 0)
			cn.Del("foo")
		}

## Please Contribute

	Not all of the commands are implemented. Only the ones I immedietly needed. Each command is
	trival to implement. If you'd like add one, please do so and send a pull request.

	The current commands are:

		Get, Set, Del, Incr, Decr

## Performance

	Right now the mutex is by far the largest bottleneck. There are thoughts on how to reduce it's impact. Any help is always appreciated.