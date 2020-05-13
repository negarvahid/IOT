var pfio = require('piface');
var http = require('http').createServer(handler);
var fs = require('fs')
var io = require('socket.io')(http);

pfio.init();
http.listen(8080);

function handler (req, res) { //create server
  fs.readFile(__dirname + '/index.html', function(err, data) { //read file index.html in public folder
    if (err) {
      res.writeHead(404, {'Content-Type': 'text/html'}); //display 404 on error
      return res.end("404 Not Found");
    }
    res.writeHead(200, {'Content-Type': 'text/html'}); //write HTML
    res.write(data); //write data from index.html
    return res.end();
  });
}

io.sockets.on('connection', function(socket) {
	var ledstatus = [0,0,0,0,0,0];
	var ledsignal = [0,0,0,0,0,0];
	
	var relaystatus = [0,0]
	var relaysignal = [0,0]
	
	socket.on('LED3', function(data) {
		ledstatus[0] = data;
		if(ledstatus[0] != 0)
		{
			if(ledsignal[0] == 0)
			{
				pfio.digital_write(2,1);
				ledsignal[0] = 1;
			}
			else
			{
				pfio.digital_write(2,0);
				ledsignal[0] = 0;
			}
		}
	});
	
	socket.on('LED4', function(data) {
		ledstatus[1] = data;
		if(ledstatus[1] != 0)
		{
			if(ledsignal[1] == 0)
			{
				pfio.digital_write(3,1);
				ledsignal[1] = 1;
			}
			else
			{
				pfio.digital_write(3,0);
				ledsignal[1] = 0;
			}
		}
	});
	
	socket.on('LED5', function(data) {
		ledstatus[2] = data;
		if(ledstatus[2] != 0)
		{
			if(ledsignal[2] == 0)
			{
				pfio.digital_write(4,1);
				ledsignal[2] = 1;
			}
			else
			{
				pfio.digital_write(4,0);
				ledsignal[2] = 0;
			}
		}
	});
	
	socket.on('LED6', function(data) {
		ledstatus[3] = data;
		if(ledstatus[3] != 0)
		{
			if(ledsignal[3] == 0)
			{
				pfio.digital_write(5,1);
				ledsignal[3] = 1;
			}
			else
			{
				pfio.digital_write(5,0);
				ledsignal[3] = 0;
			}
		}
	});

	socket.on('LED7', function(data) {
		ledstatus[4] = data;
		if(ledstatus[4] != 0)
		{
			if(ledsignal[4] == 0)
			{
				pfio.digital_write(6,1);
				ledsignal[4] = 1;
			}
			else
			{
				pfio.digital_write(6,0);
				ledsignal[4] = 0;
			}
		}
	});
	
	socket.on('LED8', function(data) {
		ledstatus[5] = data;
		if(ledstatus[5] != 0)
		{
			if(ledsignal[5] == 0)
			{
				pfio.digital_write(7,1);
				ledsignal[5] = 1;
			}
			else
			{
				pfio.digital_write(7,0);
				ledsignal[5] = 0;
			}
		}
	});
	
	socket.on('RELAY1', function(data) {
		relaystatus[0] = data;
		if(relaystatus[0] != 0)
		{
			if(relaysignal[0] == 0)
			{
				pfio.digital_write(0,1);
				relaysignal[0] = 1;
			}
			else
			{
				pfio.digital_write(0,0);
				relaysignal[0] = 0;
			}
		}
	});	
	
	socket.on('RELAY2', function(data) {
		relaystatus[1] = data;
		if(relaystatus[1] != 0)
		{
			if(relaysignal[1] == 0)
			{
				pfio.digital_write(1,1);
				relaysignal[1] = 1;
			}
			else
			{
				pfio.digital_write(1,0);
				relaysignal[1] = 0;
			}
		}
	});	
});
