// autorefreshing a web page portion

setInterval(function() {
	$.get("getLatestData.php", function (result) {
		$('#latestData').html(result);
	});
}, 1000);