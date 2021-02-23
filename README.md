# Booking App API
* Root URL: ```https://booking-app.vn/```
### API danh sách biến thể đặt lịch
* method: ```GET```
* url ```/api/variants.json?shop_domain```
* headers: ```Không có```
* shop_domain là haravan url của shop, ví dụ: ```https://booking-app.myharavan.com/``` hoặc ```https://yourdomain.com/```
* Tham khảo thêm về liqid haravan: ```https://docs.haravan.com/blogs/co-ban```

### API GET thời gian trống của các chi nhánh (locations)
* url = ```'https://booking-app.vn/api/locations.json?shop_domain={{ shop.domain }}```
* Code mẫu: 
```
<script>
                $('#booking_app_variant_submit_button').click(function () {
                    var mylist = document.getElementById("change_booking_button");
                    var variant = mylist.options[mylist.selectedIndex];
                    $("#variant_id").html('<option value="' + variant.value + '">' + variant.text + '</option>');
                    var xmlhttp = new XMLHttpRequest();
                    var url = 'https://booking-app.vn/api/locations.json?shop_domain={{ shop.domain }}';
                    xmlhttp.onreadystatechange = function () {
                        if (this.readyState == 4 && this.status == 200) {
                            var myArr = JSON.parse(this.responseText);
                            booking_app_location_Function(myArr);
                        }
                    };
                    xmlhttp.open("GET", url, true);
                    xmlhttp.send();

                    function booking_app_location_Function(myJson) {
												var shop_delivery_or_not_html = '<div class="row">\n' +
        '                            <div class="col">\n' +
        '                                <div class="p-3 mb-2">\n' +
        '                                    <input class="checkbox" type="checkbox" id="at_customer_address"\n' +
        '                                           name="at_customer_address"\n' +
        '                                           value="checked">\n' +
        '                                    <label for="at_customer_address"> Dịch vụ tận nơi</label><br>\n' +
        '                                    <div class="h5" id="customer_address_and_note" name="customer_address_and_note">\n' +
        '                                        Tới địa chỉ của {{ shop.name }}\n' +
        '                                    </div>\n' +
        '              \t\t\t\t\t\t\t\t\t\t<br>\n' +
        '                                </div>\n' +
        '                            </div>\n' +
        '                        </div>';
												if (myJson.delivery_service) {
													document.getElementById("shop_delivery_or_not").innerHTML =shop_delivery_or_not_html;
													$('#at_customer_address').click(function () {
        if ($(this).prop("checked")) {
            document.getElementById("customer_address_and_note").innerHTML = '<input type="text" class="form-control" placeholder="Điền địa chỉ của bạn!" id="booking_app_customer_address" name="booking_app_customer_address">';
        } else {
            document.getElementById("customer_address_and_note").innerHTML = "Tới địa chỉ của {{ location.name }}: {{ location.address1 }}";
        }
    });
												};
                        $("#location_id").html("")
                        $("#location_id").append('<option value="000">Chưa chọn</option>');
                        $.each(myJson.location, function (index, value) {
                            $("#location_id").append('<option value="' + value.id + '">' + value.name + '</option>');
                        });

                        $('#location_id').on('change', function () {
                            $("#free_time").html("")
                            console.log($(this).val());
                            for (var i = 0; i < myJson.location.length; i++) {
                                if (myJson.location[i].id == $(this).val()) {
                                    $.each(myJson.location[i].free_time, function (index, value) {
                                        $("#free_time").append('<option value="' + value + '">' + value + '</option>');
                                    });
                                }
                            }
                        });
                    }

                });
            </script>


```
### API tạo lịch từ theme haravan
#### POST
* method: ```POST```
* form_post: ```location_id``` ```start_time``` ```variant_id``` ```phone``` ```booking_app_customer_name```
#### Ví dụ:
* Form 
```
<!-- Bắt đầu phần Modal hiện ra block lịch, có thể thay đổi html và CSS, lưu ý các trường id của select trong mybookingappForm cần giữ nguyên -->
            {% if  product.available %}
                {% for protag in product.tags %}
                    {% if protag contains 'duration_time_' %}
                        <form id="mybookingappForm">
                            <div id="myBookingAppModal" class="booking_app_modal">
                                <!-- Modal content -->

                                <div class="booking_app_modal-body">
                                    <div class="booking_app_modal-header">
                                        <span class="booking_app_modal_close">&times;</span>
                                        <h4>Đặt lịch tại {{ shop.name }}</h4>
                                    </div>

                                    <div class="row">
                                        <div class="col">
                                            <div class="p-3 mb-2">
                                                <select id="variant_id" name="variant_id" class="next-input"
                                                        required>
                                                </select>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="row">
                                        <div class="col">
                                            <div class="p-3 mb-2">
                                                <label
                                                        class="label-input-group">Chi nhánh*</label>
                                                <div class="">
                                                    <select id="location_id" name="location_id" class="next-input"
                                                            required>
                                                        <option value="000">Chưa chọn</option>
                                                    </select>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="col">
                                            <div class="p-3 mb-2">
                                                <label
                                                        class="label-input-group">Giờ bắt đầu*</label>
                                                <div class=""><select id="free_time" name="free_time"
                                                                      class="next-input" required>

                                                </select>
                                                </div>
                                            </div>
                                        </div>
                                    </div>

                                    <div class="row">
                                        <div class="col">
                                            <div class="p-3 mb-2">
                                                <label
                                                        class="label-input-group">Họ và tên*</label>
                                                <input id="booking_app_customer_name" type="text" name="booking_app_customer_name"
                                                       class="next-input"
                                                       placeholder="Họ và Tên" required>

                                            </div>
                                        </div>
                                    </div>
                                    <div class="row">
                                        <div class="col">
                                            <div class="p-3 mb-2">
                                                <label
                                                        class="label-input-group">Số
                                                    điện
                                                    thoại*</label>
                                                <input id="phone" type="tel" name="phone"
                                                       class="next-input"
                                                       placeholder="097xxxxxxxx" pattern="[0-9]{10}" required>

                                            </div>
                                        </div>
                                    </div>
																	<br>
																	<div id="shop_delivery_or_not" name="shop_delivery_or_not">

																	</div>
                                    <br>
                                    <div class="row">
                                        <div class="col">
                                            <div class="p-3 mb-2">
                                                <button type="submit" name="book_event" id="book_event"
                                                        class="btn btn-primary btn-lg btn-block"
                                                        value="{{ variant_id }}">

                                                    BookNow
                                                </button>
                                            </div>
                                        </div>

                                    </div>


                                    <div class="booking_app_modal-footer">
                                        <h5> {{ shop.name }} Sẽ liên hệ lại với quý khách</h5>

                                    </div>

                                </div>
                            </div>

                        </form>
                    {% endif %}
                {% endfor %}
            {% endif %}
            <!-- Kết thúc phần Modal đặt lịch -->
```
* Script để post lên server booking app
```
<script>
                window.addEventListener("load", function () {
                    function sendData() {
                        const XHR = new XMLHttpRequest();

                        // Bind the FormData object and the form element
                        const FD = new FormData(form);
                        // Define what happens on successful data submission
                        XHR.addEventListener("load", function (event) {
                            alert(event.target.responseText);
                            $('#myBookingAppModal').modal('hide');
                        });

                        // Define what happens in case of error
                        XHR.addEventListener("error", function (event) {
                            alert('Có lỗi xảy ra, liên hệ shop để đặt lịch trực tiếp');
                        });

                        // Set up our request
                        XHR.open("POST", 'https://booking-app.vn/api/book');

                        // The data sent is what the user provided in the form
                        XHR.send(FD);
                    }

                    // Access the form element...
                    const form = document.getElementById("mybookingappForm");

                    // ...and take over its submit event.
                    form.addEventListener("submit", function (event) {
												alert("Server đang lên lịch! Quý khách hãy bấm OK/Đóng và chờ trong giây lát, hệ thống sẽ thông báo nếu đặt lịch thành công!");
                        event.preventDefault();
                        sendData();
                    });
                });
            </script>
            ```

