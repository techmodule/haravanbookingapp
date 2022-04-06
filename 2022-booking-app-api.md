# API KET NOI BOOKING APP TU HARAVAN

## MAIN URL:

`https://booking-app.vn/`

### REQUIRED PARAM URL

`&shop_domain={{shop.domain}}`

#### PATH URL GET LOCATIONS

`/guess/api/v1/shop/locations.json`

* method: `GET`
* Header: `Not required`
* Full url && params
  example: `https://booking-app.vn/guess/api/v1/shop/locations.json?shop_domain=https://congdongbongro.myharavan.com/&location_id=1269083&date=2022-04-06`
* Repsone Json: `status_code 200`

```json
{
  'status': true,
  'message': 'Tìm thấy shop',
  'locations': [
    {
      'id': 1269083,
      'name': 'Sân Thanh Xuân 1',
      'email': null,
      'address1': 'Lê Văn Lương, Đ. Lê Văn Lương',
      'address2': null,
      'zip': '700000',
      'city': null,
      'province': 'Hà Nội',
      'country': 'Vietnam',
      'phone': '0868831333',
      'country_code': 'VN',
      'country_name': 'Vietnam',
      'province_code': 'HI',
      'district': 'Quận Thanh Xuân',
      'district_code': 'HI7',
      'ward': 'Phường Nhân Chính',
      'ward_code': '00343',
      'is_primary': true,
      'is_unavailable_quantity': false,
      'type': 'default',
      'shop_id': 200000492057,
      'calendarId': 'mtdladjejatgkh0la6dqdemkng@group.calendar.google.com',
      'morning_start_time': '07:00:00',
      'noon_start_time': '23:00:00',
      'noon_end_time': '12:00:00',
      'after_noon_end_time': '22:00:00'
    },
    {
      'id': 1272551,
      'name': 'Sân Thanh Xuân 2',
      'email': null,
      'address1': 'Lê Văn Lương',
      'address2': null,
      'zip': '70000',
      'city': null,
      'province': 'Hà Nội',
      'country': 'Vietnam',
      'phone': '03456789',
      'country_code': 'VN',
      'country_name': 'Vietnam',
      'province_code': 'HI',
      'district': 'Quận Ba Đình',
      'district_code': 'HI2',
      'ward': 'Phường Giảng Võ',
      'ward_code': '00031',
      'is_primary': false,
      'is_unavailable_quantity': false,
      'type': 'default',
      'shop_id': 200000492057,
      'calendarId': 'dc75q1id9e4catp6pmp8kgmid8@group.calendar.google.com',
      'morning_start_time': '07:00:00',
      'noon_start_time': '12:00:00',
      'noon_end_time': '12:00:00',
      'after_noon_end_time': '22:00:00'
    }
  ]
}

```

```json

```

#### PATH URL GET LOCATION FREE_TIME

`/guess/api/v1/shop/locations.json/free_time`

* method: `GET`
* Header: `Not required`
* Full url && params
  example: `https://booking-app.vn/guess/api/v1/shop/locations.json?shop_domain=https://congdongbongro.myharavan.com/&location_id=1269083&date=2022-04-06`
* Repsone Json: `status_code 200`

```json
{
  'status': true,
  'message': 'Tìm thấy shop',
  'locations': [
    {
      'id': 1269083,
      'name': 'Sân Thanh Xuân 1',
      'email': null,
      'address1': 'Lê Văn Lương, Đ. Lê Văn Lương',
      'address2': null,
      'zip': '700000',
      'city': null,
      'province': 'Hà Nội',
      'country': 'Vietnam',
      'phone': '0868831333',
      'country_code': 'VN',
      'country_name': 'Vietnam',
      'province_code': 'HI',
      'district': 'Quận Thanh Xuân',
      'district_code': 'HI7',
      'ward': 'Phường Nhân Chính',
      'ward_code': '00343',
      'is_primary': true,
      'is_unavailable_quantity': false,
      'type': 'default',
      'shop_id': 200000492057,
      'calendarId': 'mtdladjejatgkh0la6dqdemkng@group.calendar.google.com',
      'morning_start_time': '07:00:00',
      'noon_start_time': '23:00:00',
      'noon_end_time': '12:00:00',
      'after_noon_end_time': '22:00:00',
      'free_time': [
        '2022-04-10 07:00:00',
        '2022-04-10 09:00:00',
        '2022-04-10 11:00:00',
        '2022-04-10 13:00:00',
        '2022-04-10 15:00:00',
        '2022-04-10 17:00:00',
        '2022-04-10 19:00:00',
        '2022-04-10 21:00:00'
      ],
      'free_time_css': [
        {
          'start': '2022-04-10 07:00:00',
          'end': '2022-04-10 09:00:00',
          'status': true,
          'free_slot': 1,
          'ordered_slots': 0
        },
        {
          'start': '2022-04-10 09:00:00',
          'end': '2022-04-10 11:00:00',
          'status': true,
          'free_slot': 1,
          'ordered_slots': 0
        },
        {
          'start': '2022-04-10 11:00:00',
          'end': '2022-04-10 13:00:00',
          'status': true,
          'free_slot': 1,
          'ordered_slots': 0
        },
        {
          'start': '2022-04-10 13:00:00',
          'end': '2022-04-10 15:00:00',
          'status': true,
          'free_slot': 1,
          'ordered_slots': 0
        },
        {
          'start': '2022-04-10 15:00:00',
          'end': '2022-04-10 17:00:00',
          'status': true,
          'free_slot': 1,
          'ordered_slots': 0
        },
        {
          'start': '2022-04-10 17:00:00',
          'end': '2022-04-10 19:00:00',
          'status': true,
          'free_slot': 1,
          'ordered_slots': 0
        },
        {
          'start': '2022-04-10 19:00:00',
          'end': '2022-04-10 21:00:00',
          'status': true,
          'free_slot': 1,
          'ordered_slots': 0
        },
        {
          'start': '2022-04-10 21:00:00',
          'end': '2022-04-10 23:00:00',
          'status': true,
          'free_slot': 1,
          'ordered_slots': 0
        }
      ]
    }
  ],
  'date': '2022-04-10'
}
```

#### PATH URL GET SHOP SERVICE

`/guess/api/v1/shop/services.json`

* method: `GET`
* Header: `Not required`
* Full url && params
  example: `https://booking-app.vn/guess/api/v1/shop/services.json?shop_domain=https://congdongbongro.myharavan.com/`
* Repsone Json: `status_code 200`

```json

{'status': true, 'message': 'Tìm thấy shop', 'services': [{'id': 1038648078, 'title': 'Đặt lịch sân bóng rổ', 'duration': 120, 'variants': [{'barcode': null, 'compare_at_price': 0.0, 'created_at': '2022-04-04T14:02:07.143Z', 'fulfillment_service': null, 'grams': 0.0, 'id': 1084647674, 'inventory_management': null, 'inventory_policy': 'deny', 'inventory_quantity': 0, 'position': 1, 'price': 20000.0, 'product_id': 1038648078, 'requires_shipping': false, 'sku': null, 'taxable': true, 'title': 'Bảng Giá', 'updated_at': '2022-04-06T11:32:05.245Z', 'image_id': 1243749428, 'option1': 'Bảng Giá', 'option2': null, 'option3': null, 'inventory_advance': null, 'webhook_ta: 'deny', 'inventory_quantity': 0, 'position': 1, 'price': 20000.0, 'product_id': 1038648078, 'requires_shipping': false, 'sku': null, 'taxable': true, 'title': 'Bảng Giá', 'updated_at': '2022-04-06T11:32:05.245Z', 'image_id': 1243749428, 'option1': 'Bảng Giá', 'option2': null, 'option3': null, 'inventory_advance': null, 'webhook_tags': null, 'image': {'created_at': '2022-04-05T08:00:47.115Z', 'id': 1243749428, 'position': 1, 'product_id': 1038648078, 'src': 'https://product.hstatic.net/200000492057/product/img_5226-e1509650482598-1024x772_16efbdf0be92491bb2b58bdaef6bd67d.jpeg', 'updated_at': '2022-04-05T08:01:08.876Z', 'filename': 'img_5226-e1509650482598-1024x772_16efbdf0be92491bb2b58bdaef6bd67d.jpeg', 'variant_ids': [1084647674]}}], 'images': [{'created_at': '2022-04-05T08:00:47.115Z', 'id': 1243749432, 'position': 3, 'product_id': 1038648078, 'src': 'https://product.hstatic.net/200000492057/product/hoc-nem-bong-ro_9071947c66704fa9939dcd546632b9f2.jpeg', 'updated_at': '2022-04-05T08:00:47.115Z', 'filename': 'hoc-nem-bong-ro_9071947c66704fa9939dcd546632b9f2.jpeg', 'variant_ids': []}, {'created_at': '2022-04-05T08:00:47.115Z', 'id': 1243749428, 'position': 1, 'product_id': 1038648078, 'src': 'https://product.hstatic.net/200000492057/product/img_5226-e1509650482598-1024x772_16efbdf0be92491bb2b58bdaef6bd67d.jpeg', 'updated_at': '2022-04-05T08:01:08.876Z', 'filename': 'img_5226-e1509650482598-1024x772_16efbdf0be92491bb2b58bdaef6bd67d.jpeg', 'variant_ids': [1084647674]}, {'created_at': '2022-04-05T08:00:47.115Z', 'id': 1243749430, 'position': 2, 'product_id': 1038648078, 'src': 'https://product.hstatic.net/200000492057/product/cac-bai-tap-bong-ro-co-ban_1be84d82cffd42df95dcb84499c9d7a4.jpeg', 'updated_at': '2022-04-05T08:00:47.115Z', 'filename': 'cac-bai-tap-bong-ro-co-ban_1be84d82cffd42df95dcb84499c9d7a4.jpeg', 'variant_ids': []}]}], 'date': '2022-04-06'}

```

#### PATH URL BOOKING

`/guess/api/v1/shop/book.json`

* method: `POST`
* Header: `Not required`
* Full url && params
  example: `https://booking-app.vn/guess/api/v1/shop/book.json?shop_domain=https://congdongbongro.myharavan.com/`
* Repsone Json: `status_code 201`
* POST FORM:
  `first_name`
  `last_name`
  `phone`
  `email`
  `start_time`
  `location_id`
  `variant_id`
  `duration`

* start_time format: `YYYY-MM-DD HH:mm:ss`
* duration minutes interger: `60` `90` `120` `...`
* required:
  `last_name`
  `phone`
  `start_time`
  `location_id`
  `variant_id`
  `duration`
* Example:

```javascript

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
    ;
```

* Response JSON: `status` `message` `event` `order`

```json

```

      
