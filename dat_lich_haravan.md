# CÁCH CÀI ĐẶT ỨNG DỤNG ĐẶT LỊCH LÊN WEBSITE HARAVAN
## Thiết lập dịch vụ:
### Định nghĩa sản phẩm là dịch vụ:
#### Sản phẩm có chứa tag: booking.
#### Biến thể là dịch vụ có cấu trúc sau:
##### Option1: Tên chi nhánh.
#### Option2: Năng lực / mỗi khung giờ.
#### Option3: Thời gian thi công.
## Thiết lập đặt lịch trong theme Haravan

#### Link demo: https://demo-dat-lich.myharavan.com/products/dich-vu-lam-dep-lam-trang-da-toan-than
#### Tạo 1 trang sản phẩm có tên là product.booking.liqid, copy product.liqid sang

#### Xoá nút thêm vào giỏ, mua ngay

#### Chèn đoạn code này vào vị trí cần hiển thị

```html

<div class="customize-product-slider clearfix">
    <h1 itemprop="name">Khung giờ rảnh</h1>
    <div class="pro-brand">
        <span class="title">Chọn ngày đặt lịch</span>
    </div>
    <div id="date" class="pro-short-desc">

    </div>
    <div class="pro-content-head clearfix">
        <div class="pro-brand">
            <span class="title">Chọn giờ bắt đầu:</span>
        </div>
    </div>

    <div id="free_time_render">

    </div>
</div>
<div class="contact-form">
    <form id="bookingAppForm">
        <div id="book_sucess"></div>
        <div class="title-bl">
            <h2>Thông tin của bạn</h2>
        </div>
        <div id="customer_infomations">
            <div class="row">
                <div class="col-sm-6 col-xs-12">
                    <div class="input-group">
                        <input required type="text" id="first_name"
                               name="first_name" placeholder="Họ">
                    </div>
                </div>
                <div class="col-sm-6 col-xs-12">
                    <div class="input-group">
                        <input required type="text" id="last_name"
                               name="last_name" placeholder="Tên">
                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-sm-6 col-xs-12">
                    <div class="input-group">
                        <input required type="phone" id="phone" name="phone"
                               placeholder="Di động">


                    </div>
                </div>
                <div class="col-sm-6 col-xs-12">
                    <div class="input-group">
                        <input type="email" id="email" name="email"
                               placeholder="Nhập email">
                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-sm-12 col-xs-12">
                    <div class="input-group">
                        <div class="pro-price clearfix">
                            <input height="120" class="note" type="text" id="note"
                                   name="note"
                                   placeholder="Ghi chú nếu cần thiết"></div>
                        <h6>
                            Kéo xuống và bấm vào từng dịch vụ bạn muốn đặt lịch
                        </h6>
                        <button type="button" id="book-now"
                                {% unless product.available %}disabled{% endunless %}
                                class="{% unless product.available %}disabled{% endunless %} add-to-cartProduct button dark btn-addtocart addtocart-modal {{ className }}"
                                name="add" onclick="BookNow()">Đặt ngay
                        </button>
                    </div>
                </div>

            </div>
    </form>
</div>
```

#### Chèn đoạn code này vào trong hàm chọn biến thể, ví dụ:

```javascript
 $('#add-item-form #variant-swatch-1 .swatch-element[data-value = "' + _key + '"]').addClass('soldout');
setTimeout(async function () {
    document.getElementById("free_time_render").innerHTML = '<h3>Đang tải dữ liệu</h3>';
    await VariantFreeTime();
    $('#add-item-form #variant-swatch-1 .swatch-element[data-value = "' + _key + '"] input').attr('disabled', 'disabled');
})
}
```

#### Copy code JS dưới đây vào cuối trang

#### Tìm đoạn code: var token = "WNWMHO9JPX3QUC7GP7UDICDILE1VEGSR458QUEQQDEKS7X3X9W0L1Y7XGBF4T7BX";

#### Thay token bằng Mã bảo mật kết nối đặt lịch trên website tại link https://admin.booking-app.vn/haravan_shop.html

```javascript

<script>
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
}

    function clickFreeTime(i) {
    let id_name = "free_time_item_" + i;
    var click_button = document.getElementById(id_name);
    //console.log(click_button);
    var current = document.getElementsByClassName("free_time_active");
    current[0].className = current[0].className.replace(" free_time_active", "");
    click_button.className += " free_time_active";
    //alert(i);

}

    function renderDate(date_to_change) {
    let yourDate = new Date(date_to_change)
    return yourDate.toISOString().split('T')[0]
}

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

    async function clickDate(date_id) {
    document.getElementById("free_time_render").innerHTML = '<h3>Đang tải dữ liệu</h3>';
    let id_date = "date_" + date_id;
    var date_click_button = document.getElementById(id_date);
    //console.log(date_click_button);
    var date_current = document.getElementsByClassName("btn_date_active");
    date_current[0].className = date_current[0].className.replace(" btn_date_active", "");
    date_click_button.className += " btn_date_active";
    await VariantFreeTime();
}

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
}

    async function VariantFreeTime() {
    let dates = document.getElementById("date");
    var date = dates.getElementsByClassName("btn_date_active")[0].value;
    var str_date = formatDate(date);
    //alert(str_date);
    var variant_id = $('#product-select').val()
    var new_url = "https://admin.booking-app.vn/api/haravan/variant.json";
    var token = "WNWMHO9JPX3QUC7GP7UDICDILE1VEGSR458QUEQQDEKS7X3X9W0L1Y7XGBF4T7BX";
    let new_free_time_url = new_url + '?variant_id=' + variant_id + '&date=' + str_date;
    //alert(new_free_time_url);
    var otpions = {
    method: "GET",
    mode: 'cors', // no-cors, *cors, same-origin
    cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
    credentials: 'same-origin', // include, *same-origin, omit
    headers: {
    Authorization: "Bearer " + token,
    'Content-Type': 'application/json',
    "Access-Control-Allow-Origin": "*",
}
}
    let response = await fetch(new_free_time_url, otpions);
    let repsone_json = await response.json();
    //alert("True")
    if (repsone_json.status) {
    //alert("True")
    let data = repsone_json.data;
    if (data !== null && typeof data.free_time !== "undefined" && data.free_time !== null) {
    let free_time = data.free_time;
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

} else {
    free_time_render = '<h6>Chi nhánh chưa thiết lập đặt  lịch</h6>'
}

    document.getElementById("free_time_render").innerHTML = free_time_render;
} else {
    alert(response.message);
}
    return repsone_json;
}

    function formToJson(formData) {
    var object = {};
    formData.forEach((value, key) => {
    // Reflect.has in favor of: object.hasOwnProperty(key)
    if (!Reflect.has(object, key)) {
    object[key] = value;
    return;
}
    if (!Array.isArray(object[key])) {
    object[key] = [object[key]];
}
    object[key].push(value);
});
    return object;
}

    async function BookNow() {
    //alert(variant_id);
    let book_url = "https://admin.booking-app.vn/api/haravan/book.json"
    let phone = document.getElementById("phone").value;
    let email = document.getElementById("email").value;
    let last_name = document.getElementById("last_name").value;
    if (phone === null || phone.length < 10 || last_name === "") {
    if (phone === null || phone.length < 10) {
    alert("Vui lòng nhập số điện thoại");
}else {
    alert("Vui lòng nhập tên bạn");
}
    window.scrollTo({top: 0, behavior: 'smooth'});
} else {
    //document.getElementById(button_id).innerHTML = '<h6>Đang đặt lịch</h6>';
    let free_times = free_time_render.getElementsByClassName("free_time_active");
    let start_time = null;
    if (free_times.length === 0) {
    alert("Ngày bạn chọn đã kín hoặc khóa lịch!\nVui lòng chọn ngày khác");
    window.scrollTo({top: 0, behavior: 'smooth'});
} else {
    start_time = free_time_render.getElementsByClassName("free_time_active")[0].value;
    //bookingAppForm
    let bookingAppPostForm = new FormData(bookingAppForm);
    var variant_id = $('#product-select').val();
    let data = formToJson(bookingAppPostForm);
    data.variant_id = variant_id;
    data.start_time = start_time;
    var token = "WNWMHO9JPX3QUC7GP7UDICDILE1VEGSR458QUEQQDEKS7X3X9W0L1Y7XGBF4T7BX";
    var otpions = {
    method: "POST",
    mode: 'cors', // no-cors, *cors, same-origin
    cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
    credentials: 'same-origin', // include, *same-origin, omit
    headers: {
    Authorization: "Bearer " + token,
    'Content-Type': 'application/json',
    "Access-Control-Allow-Origin": "*",
},
    body: JSON.stringify(data),
}
    await fetch(book_url, otpions)
    .then(response => response.json())
    .then(result => {
    //alert(result.message);
    if (result.status === true) {
    alert("Đặt lịch thành công");
} else {
    alert("Đặt  lịch thất bại");

}
    VariantFreeTime();
    console.log('Success:', result);
})
    .catch(error => {
    VariantFreeTime();
    alert("Xảy ra lỗi khi đặt lịch, vui lòng liên hệ shop để đặt" + error.toString());
    window.scrollTo({top: 0, behavior: 'smooth'});
});
}
}

}

    window.onload = async function () {
    document.getElementById("free_time_render").innerHTML = '<h3>Đang tải dữ liệu</h3>';
    await makeDateList();
    await VariantFreeTime();
};

</script>

```

#### Copy css vào cuối trang

```css
<
style >
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

/* Style the active class (and buttons on mouse-over) */
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

/* Style the active class (and buttons on mouse-over) */
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

/* Style the active class (and buttons on mouse-over) btn_date date_active*/
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

/* Clear floats after the columns */
.btnRow:after {
    content: "";
    display: table;
    clear: both;
}

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

/* Style the active class (and buttons on mouse-over) */
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

.card {
    width: 19%;
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

/* Style the active class (and buttons on mouse-over) */
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

<
/
style >

```