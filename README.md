# StatsD PHP Library

A simple to use library with advanced features for working with StatsD in PHP.


## Install

Via Composer

    {
        "require": {
            "league/statsd": ">=0.1"
        }
    }


## Usage

### Configuring

    $statsd = new League\StatsD\Client();
    $statsd->configure(array(
        'host' => '127.0.0.1',
        'port' => 8125,
        'namespace' => 'example'
    ));

OR

    $statsd1 = StatsD\Client::instance('server1')->configure(array(...));
    $statsd2 = StatsD\Client::instance('server2')->configure(array(...));


### Counters

    $statsd->increment('web.pageview');
    $statsd->decrement('storage.remaining');
    $statsd->increment(array(
        'first.metric',
        'second.metric'
    ), 2);
    $statsd->increment('web.clicks', 1, 0.5);


### Gauges

    $statsd->gauge('api.logged_in_users', 123456);


### Timers

    $statsd->timing('api.response_time', 256);


## Timing Blocks

    $statsd->time('api.dbcall', function () {
        // this code execution will be timed and recorded in ms
    });


## Testing

    phpunit


## TODO

- ~~Namespacing~~
- Documentation
- More Framework Integration
- Exception Handlers
- Full Unit Test Coverage


## Credits

- [Marc Qualie](https://github.com/marcqualie)
- [All Contributors](https://github.com/php-loep/php-statsd/contributors)


## Contributing

- Fork the project from [Github](https://github.com/php-loep/php-statsd)
- Create your own feature branch
- Make your changes
- Run the tests and add your own
- Push to your own fork
- Create pull request to origin repo


## License

The MIT License (MIT). Please refer to [License File](https://github.com/league/php-statsd/blob/master/LICENSE) for more information
