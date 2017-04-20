// API
    // get
    $.ajax({
        url: '/User/Get/20',
        dataType: "json",
        type: "GET",
        contentType: 'application/json; charset=utf-8',
        async: true,
        processData: false,
        cache: false,
        success: function (data) {
            alert(data);
        },
        error: function (xhr) {
            alert('error');
        }
    });

    // post
    $.ajax({
        url: '/User/Create',
        dataType: "json",
        type: "POST",
        contentType: 'application/json; charset=utf-8',
        data: JSON.stringify({user: {name: 'Rintu', email: 'Rintu@gmial.com'}}),
        // data: { productname: pname, productprice: pprice },
        // productname est ce que le server manipulera
        // pname est ce que le client envoie
        async: true,
        processData: false,
        cache: false,
        success: function (data) {
            alert(data);
        },
        error: function (xhr) {
            alert('error');
        }
    })

    // put
    $.ajax({
        url: '/User/Edit',
        dataType: "json",
        type: "PUT",
        contentType: 'application/json; charset=utf-8',
        data: JSON.stringify({id: 100, user: {name: 'Rintu', email: 'Rintu@gmial.com'}}),
        async: true,
        processData: false,
        cache: false,
        success: function (data) {
            alert(data);
        },
        error: function (xhr) {
            alert('error');
        }
    });

    // delete
    $.ajax({
        url: '/User/Delete',
        dataType: "json",
        type: "DELETE",
        contentType: 'application/json; charset=utf-8',
        data: JSON.stringify({id: 20}),
        async: true,
        processData: false,
        cache: false,
        success: function (data) {
            alert(data);
        },
        error: function (xhr) {
            alert('error');
        }
    });
