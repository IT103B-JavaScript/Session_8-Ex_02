- Xác định lỗi sai - Phân tích nguyên nhân:
    + Lỗi 1:
    => Dòng gây lỗi: const xeVaoSac = hangDoiXeCho.pop();
    => Nguyên nhân:  sử dụng sai cú pháp để lấy ra xe vào sạc, xe ở cuỗi hàng lại được sạc trước xe  ở đầu hàng, phi phạm nghiêm trọng nguyên tắc điều phối
    => Cách xử lí: thay thế cú pháp pop() thành shift() -> const xeVaoSac = hangDoiXeCho.shift()

    + Lỗi 2:
    => Dòng gây lỗi: for (let i = 0; i <= hangDoiXeCho.length; i++)
    => Nguyên nhân gây lỗi: Do việc đặt sai điều kiện vòng lặp, nên số lượng được in ra sai so với mong muốn, do vòng lặp đang thực hiện từ i=0 nên việc chạy đến <= hangDoiXeCho.length gây ra thừa 1 vòng lặp.
    => Cách xử lí: ta có thể xử lí theo 2 cách
        . Thay đổi i=0 thành i=1 lúc này thì vòng lặp đang chạy từ thứ tự đầu tiên đến thứ tự cuối cùng của hàng đợi giống như cách ta nói bằng văn nói
        . Thay đổi điều kiện lặo thành: i < hangDoiXeCho.length lúc này nó sẽ hiểu vòng lặp chạy từ vị trí số 0 đến vị trí số hangDoiXeCho.length - 1 đảm bảo đủ số lượng vòng lặp
- Bảng test case:

|Trường hợp kiểm thử|Dữ liệu đầu vào|Kết quả sai thực tế|Kết quả đúng mong đợi|
|---|---|---|---|
|Giống như số liệu ban đầu của đề bài|const hangDoiXeCho = ['30A-98765', '29B-12345', '51C-45678']; <br> hangDoiXeCho.push('43D-88888')|STT 1: 30A-98765 <br> STT 2: 29B-12345 <br> STT 3: 43D-88888 <br> STT 4: undefined|STT 1: 29B-12345 <br> STT 2: 51C-45678 <br> STT 3: 43D-88888|
|Trường hợp thay đổi xe thêm vào cuối|const hangDoiXeCho = ['30A-98765', '29B-12345', '51C-45678']; <br> hangDoiXeCho.push('43D-88888')|STT 1: 30A-98765 <br> STT 2: 29B-12345 <br> STT 3: 66MD-9999 <br> STT 4: undefined|STT 1: 29B-12345  <br> STT 2: 51C-45678 <br> STT 3: 66MD-9999|