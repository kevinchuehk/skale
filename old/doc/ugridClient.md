## UgridClient class
Example:

	var UgridClient = require('ugrid-client');
	var grid = new UgridClient({
		host: 'localhost',
		port: 12346,
		data: {type: 'worker'}
	});

## wsConnect_cb([callback])
Example:

	grid.wsConnect_cb(function (err, res) {
		console.log("Connected as " + ' ' + res.uuid);
	};

## connect_cb([callback])
Example:

	grid.connect_cb(function (err, res) {
		console.log("Connected as " + ' ' + res.uuid);
	};

## disconnect()
Example:

	grid.disconnect();

## send_cb(uuid, object, [callback])
Example:

	grid.send_cb(0, {cmd: 'hello', data: "world"}, function (err, res) {
		console.log("message sent");
	});

## devices_cb(object, [number], [callback])
Example:

	grid.devices_cb({type: 'worker'}, function (err, res) {
		console.log(res.length + " workers are connected");
	});

## on(event, callback(msg))
Example:

	grid.on("hello", callback(msg) {
		grid.reply_cb(msg, null, "Welcome");
	});

## publish_cb(data, [callback])
Example:

   grid.publish_cb(count++);

## request_cb(host, data, [callback])
Example:

	grid.devices_cb({type: 'worker'}, 2, function (err, res) {
		grid.request_cb(worker[1], "hello", function (err2, res2) {
			console.log("response from worker[1]: " + res2);
		});
	});

## reply_cb(msg, error, data, [callback])