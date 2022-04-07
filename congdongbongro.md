# Bàn giao hướng dẫn sử dụng đặt lịch bóng rổ

## Luồng hoạt động

### Bien san pham thanh dinh vu voi the tag: duration_time_

`Vi du : duation_time_60 thi san pham day tro thanh dich vu co thoi gian thuc hien la 60 PHUT Luu y: Tat ca bien the deu
tro thanh dich vu voi thoi gian tuong tu``

### Cơ chế sử dụng templale liquid cho trang nội dung.

#### Link truy cập tạo trang đặt lịch:

https://congdongbongro.myharavan.com/admin/sale_channels/web/pages

#### Ví dụ

https://congdongbongro.myharavan.com/admin/sale_channels/web/pages/1002429134

#### Không điền nội dung trang, mà chọn giao diện page.booking-app ở góc dưới menu phải.

### Chỉnh sửa template:

#### Truy cập

https://congdongbongro.myharavan.com/admin/sale_channels/web/themes/1000844549/edit

#### Menu trái chọn page.booking-app.liquid.
###### Code mau cua theme supllo: `https://github.com/techmodule/haravanbookingapp/blob/main/booking-app.liqid-suplo.md`

#### Chỉnh sửa css để đổi màu (dưới cùng của code):

```css
.hotline {
    border: none;
    color: #333333;
    padding: 1px 5px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 13px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Nut bam hotline cua chi nhanh */
.hotline_active, .hotline:hover {
    background-color: #FFFF00;
    border: none;
    color: #333333;
    padding: 5px 15px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Nut bam hotline cua chi nhanh */

.btn_loccation {
    background-color: #4CAF50;
    border: none;
    color: white;
    padding: 1px 5px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 13px;
    margin: 4px 2px;
    cursor: pointer;
    width: 50%;
}

/* Nut bam chon chi nhanh */
.btn_loccation_active, .btn_loccation:hover {
    background-color: #FFFF00;
    border: none;
    color: #333333;
    padding: 5px 10px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 15px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Nut bam chon chi nhanh */
.btn_free_time {
    background-color: #4CAF50;
    width: 18%;
    border: none;
    color: white;
    padding: 1px 2px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Nut bam cua phan chon thoi gian */
.free_time_active, .btn_free_time:hover {
    background-color: #FFFF00;
    border: none;
    color: #333333;
    padding: 2px 5px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Nut bam cua phan chon thoi gian */
.btn_date {
    background-color: #4CAF50;
    width: 18%;
    border: none;
    color: white;
    padding: 1px 2px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 10px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Nut bam cua phan chon ngay*/
.btn_date_active, .btn_date:hover {
    background-color: #FFFF00;
    border: none;
    color: #333333;
    padding: 2px 5px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 11px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Nut bam cua phan chon thoi gian */
/* Clear floats after the columns */
.btnRow:after {
    content: "";
    display: table;
    clear: both;
}

/* block chon thoi gian */
.service_header {
    background-color: #333333;
    width: 100%;
    border-bottom: 1px solid #666;
    color: white;
    text-align: left;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    cursor: pointer;
    padding-left: 5px;
}

/* header cua dich vu can dat lich */
.btn_wrap {
    width: 30%;
    padding: 1px 2px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Phan nut bam DAT LICH*/
.btn_variant {
    background-color: #4CAF50;
    width: 30%;
    border: none;
    color: white;
    padding: 1px 2px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Phan nut bam DAT LICH*/
/* Style the active class (and buttons on mouse-over) */
.variant_active, .btn_variant:hover {
    background-color: #FFFF00;
    border: none;
    color: #333333;
    padding: 5px 15px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Phan nut bam DAT LICH*/
.card {
    width: 30%;
    border: none;
    color: white;
    padding: 1px 2px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Block hien tung thi dich vu*/
.price {
    color: grey;
    font-size: 22px;
}

.card button {
    border: none;
    outline: 0;
    padding: 12px;
    color: white;
    background-color: #000;
    text-align: center;
    cursor: pointer;
    width: 90%;
    font-size: 18px;
}

/* Block hien tung thi dich vu*/
.card button:hover {
    opacity: 0.7;
}

.cardMobile {
    width: 45%;
    border: none;
    color: white;
    padding: 1px 2px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Block hien tung thi dich vu hien thi mobile*/
.price {
    color: grey;
    font-size: 22px;
}

.cardMobile button {
    border: none;
    outline: 0;
    padding: 12px;
    color: white;
    background-color: #000;
    text-align: center;
    cursor: pointer;
    width: 90%;
    font-size: 18px;
}

.cardMobile button:hover {
    opacity: 0.7;
}

.btn_book {
    background-color: #4CAF50;
    width: 30%;
    border: none;
    color: white;
    padding: 1px 2px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
}

/* Nut bam dat lich*/
.btn_book_active, .btn_book:hover {
    background-color: #666;
    border: none;
    color: white;
    padding: 2px 5px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
}

.note {
    width: 100%;
    height: 100px;
}
```

### Phần jscript để kết nối API

```javascript
    var shop_domain = 'https://congdongbongro.myharavan.com/';
//co the thay bang voi dau {{shop.domain}}
var main_url = 'https://booking-app.vn';
var url = 'https://booking-app.vn/guess/api/v1/shop/locations.json?shop_domain=' + shop_domain;
let free_time_url = 'https://booking-app.vn/guess/api/v1/shop/locations.json/free_time?shop_domain=' + shop_domain;
let sevices_url = 'https://booking-app.vn/guess/api/v1/shop/services.json?shop_domain=' + shop_domain;
let book_url = 'https://booking-app.vn/guess/api/v1/shop/book.json?shop_domain=' + shop_domain;

//Ham lay du lieu luc bat dau load trang
async function firstLoadData(service) {
    document.getElementById("free_time_render").innerHTML = '<h3>Đang tải dữ liệu</h3>';
    makeDateList();
    let location_id = await fetchLocations(url);
    date = new Date();
    await fetchLocationsFreeTime(free_time_url, location_id, formatDate(date));
    await fetchShopServices(sevices_url);
};
//Ham lay du lieu luc bat dau load trang
window.onload = async function () {
    await firstLoadData();
};

//Ham convert thoi gian dat lich tu minutes sang hours/minutes o phan hien thi variant dich vuj
function MinutesToHours(minutes) {
    var h = Math.floor(minutes / 60);
    var m = minutes % 60;
    h_string = h < 10 ? h === 0 ? '' : '0' + h + 'h' : h + 'h';
    m_string = m < 10 ? m === 0 ? '' : '0' + m + 'p' : m + 'p';
    return h_string + m_string;
};

//Ham hien thui cac dich vu cua shop
function renderService(service) {

    let render_services = '<div class="service_header"><h3>' + service.title + '</h3></div>';
    let itemPerRow = 3;
    let check_mobile = detectMob();
    if (check_mobile) {
        itemPerRow = 2;
    }
    var variants_grid = makeListByItemPerRow(service.variants, itemPerRow);
    //console.log(variants_grid);
    let i = 0;
    let render_variants = '<div>';
    for (var variant_row of variants_grid) {
        var variant_row_render = '<div class="btnRow">';
        for (var item of variant_row) {
            let image_src = null;
            if (item.image !== null) {
                image_src = item.image.src;
            }
            let free_times = free_time_render.getElementsByClassName("free_time_active");

            let start_time = '';
            if (free_times.length > 0) {
                start_time = getElementsByClassName("free_time_active")[0].value
            }
            let render_button = '<button onclick="BookNow(' + item.id + ',' + service.duration + ')" id="variant_id_' + item.id + '"class="btn_book" >Đặt ngay</button>';
            if (i === 0) {
                render_button = '<button onclick="BookNow(' + item.id + ',' + service.duration + ')"id="variant_id_' + item.id + '"class="btn_book btn_book_active" >Đặt ngay</button>';
            }
            let render_variant = '<div class="card">' + '<img src="' + image_src + '" alt="Denim Jeans" style="width:100%">' +
                '<h1>' + item.title + '</h1>' +
                '<p class="price">' + item.price.toLocaleString('vi') + 'đ/' + MinutesToHours(service.duration) + '</p>' +
                '<p>' + render_button + '</p></div>';


            if (check_mobile) {
                render_variant = '<div class="cardMobile">' + '<img src="' + image_src + '" alt="Denim Jeans" style="width:100%">' +
                    '<h1>' + item.title + '</h1>' +
                    '<p class="price">' + item.price.toLocaleString('vi') + 'đ</p>' +
                    '<p class="price">' + MinutesToHours(service.duration) + '</p>' +
                    '<p id="start_time" class="price">' + start_time + '</p>' +
                    '<p>' + render_button + '</p></div>';
            }
            variant_row_render = variant_row_render + render_variant;
            i = i + 1;

        }
        variant_row_render = variant_row_render + '</div>';
        render_variants = render_variants + variant_row_render;
    }
    render_variants = render_variants + '</div>';
    render_services = render_services + render_variants + '</div>';

    console.log(render_services);
    return render_services;
};

//Ham lay danh sach cac chi nhanh

async function fetchLocations(url) {
    let response = await fetch(url);
    let repsone_json = await response.json();
    //console.log(repsone_json);
    let location_id = null;
    if (repsone_json.status) {

        var free_time_grid_view = "";
        var locations = repsone_json.locations;
        var current_location = locations[0];
        location_id = current_location.id;

        let location_button = '';
        let i = 0;
        for (const location of locations) {
            if (i === 0) {
                location_button = location_button + '<button value="' + location.id + '" onclick="clickLocation(' + location.id + ')" id="location_' + location.id + '"class="btn_loccation btn_loccation_active">' + location.name + '</button>';
            } else {
                location_button = location_button + '<button value="' + location.id + '" onclick="clickLocation(' + location.id + ')" id="location_' + location.id + '"class="btn_loccation">' + location.name + '</button>';
            }

            i = i + 1;
        }
        document.getElementById("locations").innerHTML = location_button;


    } else {
        alert(response.message);
    }
    return location_id;
};

//Ham convert convert thoi gian de gui len server
function formatDate(date) {
    var d = new Date(date),
        month = '' + (d.getMonth() + 1),
        day = '' + d.getDate(),
        year = d.getFullYear();

    if (month.length < 2)
        month = '0' + month;
    if (day.length < 2)
        day = '0' + day;

    return [year, month, day].join('-');
};

function renderDate(date_to_change) {
    let yourDate = new Date(date_to_change);
    return yourDate.toISOString().split('T')[0]
};

async function fetchShopServices(service_url) {
    let response = await fetch(service_url);
    let repsone_json = await response.json();
    let render_services = '<div>';
    for (let service of repsone_json.services) {
        let render_sevice_item = renderService(service);
        render_services = render_services + render_sevice_item;
    }
    render_services = render_services + '</div>';
    document.getElementById("services").innerHTML = render_services;
}

function renderSuscess(event, order) {
    return '<div><h3>Đặt lịch thành công</h3>' +
        '<h5>' + event.summary + '</h5>' +
        '<h5>Bắt đầu ' + event.start + '</h5>' +
        '<h5>Kết thúc ' + event.end + '</h5>' +
        '<h5> Mã đơn hàng ' + order.name + '</h5>' +
        '</div>';
};

function renderFail(message) {
    return '<div><h3>Xảy ra lỗi</h3>' +
        '<h5>' + message + '</h5>' +
        '</div>';
};

async function BookNow(variant_id, duration) {
    //alert(variant_id);
    let phone = document.getElementById("phone").value;
    let email = document.getElementById("email").value;
    let last_name = document.getElementById("last_name").value;
    if (phone === null || phone.length < 10 || last_name === "" || email === null || email.length < 5 || !email.includes("@") === "" || !email.includes(".") === "") {
        if (phone === null || phone.length < 10) {
            alert("Vui lòng nhập số điện thoại");
        }

        if (email === null || email.length < 5 || !email.includes("@") === "" || !email.includes(".") === "") {
            alert("Vui lòng nhập nhập Email và đúng định dạng");
        } else {
            alert("Vui lòng nhập tên bạn");
        }
        window.scrollTo({top: 0, behavior: 'smooth'});
    } else {
        button_id = 'variant_id_' + variant_id;
        document.getElementById(button_id).innerHTML = '<h6>Đang đặt lịch</h6>';
        var location_id = locations.getElementsByClassName("btn_loccation_active")[0].value;
        let free_times = free_time_render.getElementsByClassName("free_time_active");

        let start_time = null;
        if (free_times.length === 0) {
            alert("Ngày bạn chọn đã kín hoặc khóa lịch!\nVui lòng chọn ngày khác");
            window.scrollTo({top: 0, behavior: 'smooth'});
        } else {
            start_time = free_time_render.getElementsByClassName("free_time_active")[0].value;

            //bookingAppForm
            let bookingAppPostForm = new FormData(bookingAppForm);
            bookingAppPostForm.append("variant_id", variant_id);
            bookingAppPostForm.append("duration", duration);
            bookingAppPostForm.append("location_id", location_id);
            bookingAppPostForm.append("start_time", start_time);
            await fetch(book_url, {
                method: 'POST',
                body: bookingAppPostForm,
            })
                .then(response => response.json())
                .then(result => {
                    alert(result.message);
                    if (result.status === true) {
                        document.getElementById("book_sucess").innerHTML = renderSuscess(result.event, result.order);
                    } else {
                        document.getElementById("services").innerHTML = renderFail(result.message);
                        window.scrollTo({top: 0, behavior: 'smooth'});

                    }

                    firstLoadData();
                    console.log('Success:', result);
                })
                .catch(error => {
                    firstLoadData();
                    alert("Xảy ra lỗi khi đặt lịch, vui lòng liên hệ shop để đặt" + error.toString());
                    document.getElementById("services").innerHTML = renderFail("Xảy ra lỗi khi đặt lịch, vui lòng liên hệ shop để đặt");
                    window.scrollTo({top: 0, behavior: 'smooth'});
                });
        }
    }

}

// Ham lay thoi gian ranh cua chi nhanh theo location_id cua chi nhanh (bigint) va date for mat YYYY-MM-DD
async function fetchLocationsFreeTime(new_url, new_location_id, date) {
    let new_free_time_url = new_url + '&location_id=' + new_location_id + '&date=' + date;
    let response = await fetch(new_free_time_url);
    let repsone_json = await response.json();
    //console.log(repsone_json);
    if (repsone_json.status) {

        let location = repsone_json.locations[0];
        document.getElementById("location_title").innerHTML = '<span id="location_title" class="title">Đang chọn: ' + location.name + '</span>';
        var address = '<div class="product-hotline">Địa chỉ: ' + location.address1 + '<a></a></div>'
        var address_2 = '<div class="product-hotline">' + location.ward + ', ' + location.district + ', ' + location.province + ', ' + ' <a></a></div>'
        var hotline = '<div class="product-hotline">Hotline: <a class="hotline" href="tel:' + location.phone + '">' + location.phone + '</a></div>'
        document.getElementById("address2").innerHTML = address_2;
        document.getElementById("address").innerHTML = address;
        document.getElementById("hotline").innerHTML = hotline;
        let free_time = location.free_time;
        var free_time_render = '';
        if (free_time.length === 0) {
            free_time_render = '<h6>Ngày này đã kín lịch, vui lòng chọn ngày khác</h6>'
        } else {
            //console.log(free_time);
            var free_time_grid = makeListByItemPerRow(free_time, 5);

            let i = 0
            for (var free_time_row of free_time_grid) {
                var free_time_row_render = '<div class="btnRow">';
                for (var item of free_time_row) {
                    var time_hour = item.substring(11, 16);

                    var free_time_element = '<button value="' + item + '" onclick="clickFreeTime(' + i + ')" id="free_time_item_' + i + '"class="btn_free_time" >' + time_hour + '</button>';
                    if (i === 0) {

                        free_time_element = '<button value="' + item + '" onclick="clickFreeTime(' + i + ')" id="free_time_item_' + i + '"class="btn_free_time free_time_active" >' + time_hour + '</button>';
                    }
                    free_time_row_render = free_time_row_render + free_time_element;
                    i = i + 1;


                }
                i = i + 1;
                free_time_row_render = free_time_row_render + '</div>'
                free_time_render = free_time_render + free_time_row_render;

            }
        }
        document.getElementById("free_time_render").innerHTML = free_time_render;
    } else {
        alert(response.message);
    }
    return repsone_json;
};

//Ham kiem tra co phai la mobile hay la desktop
function detectMob() {
    let isMobile = false;
    try {
        isMobile = window.matchMedia("only screen and (max-width: 760px)").matches;
    } catch (e) {
        console.log(e)
    }

    return isMobile;
}

//Ham chia cac thoi gian ranh theo tung hang va cot
function makeListByItemPerRow(itemList, itemPerRow) {
    let list_len = 100;
    if (itemList.isArray) {
        list_len = itemList.length;
    }
    var _mod = list_len % itemPerRow;
    var maxlength = (list_len - (list_len % itemPerRow));
    if (_mod > 0) {
        maxlength = maxlength + 1;
    }
    var newlist = [];
    for (var i = 0; i < maxlength; i++) {
        var start = i * itemPerRow;
        var end = (i + 1) * itemPerRow;
        if (end > maxlength) {
            end = itemList.length;
        }
        let element = itemList.slice(start, end);
        if (element.length > 0) {
            newlist.push(element);
        }

    }
    return newlist;
};

//Ham tao danh asch cac ngay de chon
function makeDateList() {
    var date_render = '<div class="btnRow">';

    for (var i = 0; i < 10; i++) {
        date = new Date();
        date.setDate(date.getDate() + i);
        var string_date = renderDate(date);
        var date_element = '<button value="' + string_date + '" onclick="clickDate(' + i + ')" id="date_' + i + '"class="btn_date" >' + string_date + '</button>';
        if (i === 0) {
            date_element = '<button value="' + string_date + '" onclick="clickDate(' + i + ')" id="date_' + i + '"class="btn_date btn_date_active" >' + string_date + '</button>';
        }
        date_render = date_render + date_element;
    }
    date_render = date_render + '</div>'
    document.getElementById("date").innerHTML = date_render;
}

//Ham khi bam chon ngay
async function clickDate(date_id) {
    document.getElementById("free_time_render").innerHTML = '<h3>Đang tải dữ liệu</h3>';
    let id_date = "date_" + date_id;
    var date_click_button = document.getElementById(id_date);
    //console.log(date_click_button);
    var date_current = document.getElementsByClassName("btn_date_active");
    date_current[0].className = date_current[0].className.replace(" btn_date_active", "");
    date_click_button.className += " btn_date_active";
    let locations = document.getElementById("locations");
    let location = locations.getElementsByClassName("btn_loccation_active");
    var location_id = locations.getElementsByClassName("btn_loccation_active")[0].value;
    formated_date = formatDate(date_click_button.value);
    await fetchLocationsFreeTime(free_time_url, location_id, formated_date);

}

//Ham khi bam chon chi nhanh
async function clickLocation(location_id) {
    document.getElementById("free_time_render").innerHTML = '<h3>Đang tải dữ liệu</h3>';
    let id_name = "location_" + location_id;
    var location_click_button = document.getElementById(id_name);
    //console.log(location_click_button);
    var location_current = document.getElementsByClassName("btn_loccation_active");
    location_current[0].className = location_current[0].className.replace(" btn_loccation_active", "");
    location_click_button.className += " btn_loccation_active";
    var current_date = document.getElementById("date");
    //console.log(current_date);
    var current_date = document.getElementsByClassName("btn_date_active")[0].value;
    //alert(current_date);
    await fetchLocationsFreeTime(free_time_url, location_id, formatDate(current_date));


}

//ham khi bam chon thoi gian
function clickFreeTime(i) {
    let id_name = "free_time_item_" + i;
    var click_button = document.getElementById(id_name);
    //console.log(click_button);
    var current = document.getElementsByClassName("free_time_active");
    current[0].className = current[0].className.replace(" free_time_active", "");
    click_button.className += " free_time_active";
    //alert(i);

}
```

#### Danh sach cac <div> id o phan html, chi quan tam ID, class co the thay doi theo tung theme

##### Block hien thi ngay de chon

```html

<div id="date" class="pro-short-desc"></div>

```

##### Block hien thi thoi gian ranh de chon

```html

<div id="free_time_render"></div>                             
```

##### Block hien thi danh sach chi nhanh, dia chi chi nhanh dang chon, hotline

```html

<div id="locations"></div>
<div id="address"></div>
<div id="address2"></div>
<div id="hotline"></div>                         
```

##### Block hien thi dien thong tin Ho/Ten/Phone/Email/Ghi chu, luu y id khong duoc thay doi

```html

<form id="bookingAppForm">
    <div id="customer_infomations">
        <div class="pro-price clearfix">
            <input required type="text" id="first_name" name="first_name" placeholder="Họ">
            <input required type="text" id="last_name" name="last_name" placeholder="Tên">

        </div>

        <div class="pro-price clearfix">
            <input required type="phone" id="phone" name="phone" placeholder="Di động">
            <input required type="email" id="email" name="email" placeholder="Nhập email">
        </div>
        <div class="pro-price clearfix">
            <input class="note" type="text" id="note" name="note" placeholder="Ghi chú nếu cần thiết"></div>
        <h6>
            Kéo xuống và bấm vào từng dịch vụ bạn muốn đặt lịch
        </h6>

    </div>
</form>                          
```

##### Hien thi danh sach cac dich vu cua chi nhanh, va thong bao khi dat lich thanh cong

```html

<div id="services"></div>
<div id="book_sucess"></div>
```

