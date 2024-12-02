---
name: Blockstream Green - Desktop
description: Sử dụng phần mềm Ví Green trên máy tính
---
![cover](assets/cover.webp)

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng phần mềm Blockstream Green trên máy tính để quản lý một ví an toàn trên ví cứng. Khi sử dụng ví cứng, việc sử dụng phần mềm trên máy tính của bạn để quản lý ví này là rất quan trọng. Phần mềm quản lý này không có quyền truy cập vào khóa riêng; nó chỉ được sử dụng để kiểm tra số dư của ví, tạo địa chỉ nhận và xây dựng và phát sóng các giao dịch sẽ được ví cứng ký. Green đại diện cho một trong nhiều giải pháp có sẵn để quản lý ví Bitcoin cứng của bạn.

Vào năm 2024, Blockstream Green chỉ tương thích với các thiết bị Ledger Nano S (phiên bản cũ), Ledger Nano X, Trezor One, Trezor T và Blockstream Jade.

## Giới thiệu về Blockstream Green

Blockstream Green là phần mềm có sẵn trên cả di động và máy tính. Trước đây được biết đến với tên gọi Green Address, ví này trở thành một dự án của Blockstream sau khi được mua lại vào năm 2016.

Green là một ứng dụng rất thân thiện với người dùng, làm cho nó đặc biệt phù hợp với người mới bắt đầu. Nó cung cấp các tính năng đa dạng, như quản lý ví nóng, ví cứng, cũng như ví trên chuỗi phụ Liquid. Bạn cũng có thể sử dụng nó để thiết lập một ví chỉ xem.

![GREEN-DESKTOP](assets/fr/01.webp)

Trong hướng dẫn này, chúng ta sẽ chỉ tập trung vào việc sử dụng phần mềm trên máy tính. Để khám phá các cách sử dụng Green khác, tôi mời bạn xem các hướng dẫn chuyên dụng khác của chúng tôi:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Cài đặt và Thiết lập Phần mềm Blockstream Green

Bắt đầu bằng cách cài đặt phần mềm Blockstream Green trên máy tính của bạn. Truy cập [trang web chính thức](https://blockstream.com/green/) và nhấp vào nút "*Download Now*". Sau đó, làm theo quy trình cài đặt theo hệ điều hành của bạn.

![GREEN-DESKTOP](assets/fr/02.webp)

Khởi chạy ứng dụng, sau đó đánh dấu vào ô "*I accept the terms...*".

![GREEN-DESKTOP](assets/fr/03.webp)

Khi bạn mở Green lần đầu tiên, màn hình chính hiện ra mà không có ví nào được cấu hình. Sau này, nếu bạn tạo hoặc nhập ví, chúng sẽ xuất hiện trong giao diện này. Trước khi chuyển sang tạo ví, tôi khuyên bạn nên điều chỉnh cài đặt của ứng dụng theo mong đợi của bạn. Nhấp vào biểu tượng cài đặt ở góc dưới bên trái.

![GREEN-DESKTOP](assets/fr/04.webp)

Trong menu "*General*", bạn có thể thay đổi ngôn ngữ phần mềm và kích hoạt các tính năng thử nghiệm nếu bạn muốn.

![GREEN-DESKTOP](assets/fr/05.webp)
Trong menu "*Network*", bạn có thể kích hoạt kết nối qua Tor, một mạng mã hóa tất cả các kết nối của bạn và làm cho các hoạt động của bạn khó theo dõi hơn. Mặc dù tùy chọn này có thể làm chậm hiệu suất ứng dụng một chút, nhưng nó được khuyến nghị cao để bảo vệ sự riêng tư của bạn, đặc biệt nếu bạn không sử dụng full node của riêng mình.
![GREEN-DESKTOP](assets/fr/06.webp)

Đối với những người dùng có full node của riêng mình, Green cung cấp khả năng kết nối với nó qua một máy chủ Electrum, đảm bảo kiểm soát đầy đủ thông tin mạng Bitcoin và phát sóng giao dịch. Để làm điều này, nhấp vào menu "*Custom servers and validation*", sau đó nhập thông tin máy chủ Electrum của bạn.

![GREEN-DESKTOP](assets/fr/07.webp)
Một tính năng thay thế khác là tùy chọn "*Xác minh SPV*" (SPV Verification), cho phép xác minh trực tiếp một số dữ liệu blockchain, giảm bớt nhu cầu phải tin tưởng vào nút mặc định của Blockstream, mặc dù phương pháp này không cung cấp tất cả các bảo đảm của một nút đầy đủ. Tùy chọn này cũng được tìm thấy trong menu "*Máy chủ và xác minh tùy chỉnh*" (Custom servers and validation).
![GREEN-DESKTOP](assets/fr/08.webp)

Sau khi điều chỉnh các cài đặt này theo nhu cầu của bạn, bạn có thể thoát khỏi giao diện này.

## Nhập một Ví Bitcoin vào Blockstream Green

Bây giờ bạn đã sẵn sàng để nhập ví Bitcoin của mình. Nhấn vào nút "**Bắt Đầu**" (Get Started).

![GREEN-DESKTOP](assets/fr/09.webp)

Bạn có sự lựa chọn giữa việc tạo một ví phần mềm cục bộ hoặc quản lý một ví lạnh thông qua một ví cứng. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc quản lý một ví cứng, vì vậy bạn sẽ cần chọn tùy chọn "*Trên Ví Cứng*" (On Hardware Wallet).

Tùy chọn "*Chỉ Xem*" (Watch-only), ngược lại, cho phép bạn nhập một khóa công khai mở rộng (`xpub`) để xem các giao dịch của một ví mà không thể chi tiêu các quỹ liên quan.

![GREEN-DESKTOP](assets/fr/10.webp)

Nếu bạn đang sử dụng Jade, nhấn vào nút tương ứng. Nếu không, chọn "*Kết nối một Thiết bị Cứng khác*" (Connect a different Hardware Device). Trong trường hợp của tôi, tôi đang sử dụng Ledger Nano S. Đối với người dùng Ledger, hãy chắc chắn cài đặt ứng dụng "*Bitcoin Legacy*" trên ví cứng của bạn, vì Green chỉ hỗ trợ phiên bản này.

![GREEN-DESKTOP](assets/fr/11.webp)

Kết nối ví cứng của bạn với máy tính và chọn nó trên Green.

![GREEN-DESKTOP](assets/fr/12.webp)

Chờ đợi trong khi Green nhập thông tin từ ví của bạn, sau đó bạn sẽ có thể truy cập vào nó.

![GREEN-DESKTOP](assets/fr/13.webp)

Tại thời điểm này, có hai kịch bản có thể xảy ra. Nếu bạn đã sử dụng ví cứng của mình trước đó, bạn sẽ thấy tài khoản của mình xuất hiện trên phần mềm. Nhưng nếu, giống như tôi, bạn mới chỉ khởi tạo ví cứng của mình bằng cách tạo một cụm từ ghi nhớ mà chưa sử dụng nó, bạn sẽ cần tạo một tài khoản. Nhấn vào "*Tạo Tài Khoản*" (Create Account).
![GREEN-DESKTOP](assets/fr/14.webp)
Chọn "*Tiêu Chuẩn*" (Standard) nếu bạn muốn sử dụng một ví cổ điển.

![GREEN-DESKTOP](assets/fr/15.webp)

Bây giờ bạn đã có quyền truy cập vào tài khoản của mình.

![GREEN-DESKTOP](assets/fr/16.webp)

## Sử dụng một ví cứng với Blockstream Green

Bây giờ khi ví Bitcoin của bạn đã được thiết lập, bạn đã sẵn sàng để nhận sats đầu tiên của mình! Để làm điều này, chỉ cần nhấn vào nút "*Nhận*" (Receive).

![GREEN-DESKTOP](assets/fr/17.webp)

Nhấn vào nút "*Sao chép địa chỉ*" (Copy address) để sao chép địa chỉ, hoặc quét mã QR của nó.

![GREEN-DESKTOP](assets/fr/18.webp)

Một khi giao dịch được phát sóng trên mạng, nó sẽ xuất hiện trong ví của bạn. Đợi để nhận đủ xác nhận để coi giao dịch là không thể thay đổi.

![GREEN-DESKTOP](assets/fr/19.webp)

Với bitcoin trong ví của bạn, bạn giờ đây có thể gửi chúng. Nhấn vào nút "*Gửi*" (Send).

![GREEN-DESKTOP](assets/fr/20.webp)

Trên trang tiếp theo, nhập địa chỉ của người nhận. Bạn có thể nhập nó thủ công hoặc quét mã QR bằng webcam của bạn.

![GREEN-DESKTOP](assets/fr/21.webp)

Chọn số tiền thanh toán.

![GREEN-DESKTOP](assets/fr/22.webp)
Ở phía dưới của màn hình, bạn có thể chọn mức phí cho giao dịch này. Bạn có lựa chọn tuân theo khuyến nghị của ứng dụng hoặc tự tùy chỉnh phí của mình. Phí càng cao so với các giao dịch đang chờ khác, giao dịch của bạn sẽ được xử lý nhanh hơn. Để biết thị trường phí, bạn có thể truy cập [Mempool.space](https://mempool.space/) trong phần "*Phí Giao Dịch*".
![GREEN-DESKTOP](assets/fr/23.webp)

Nếu bạn muốn cụ thể chọn các UTXO để sử dụng trong giao dịch của mình, nhấn vào nút "*Chọn coin thủ công*".

![GREEN-DESKTOP](assets/fr/24.webp)

Kiểm tra cài đặt của giao dịch và, nếu mọi thứ đều như bạn mong đợi, nhấn vào "*Tiếp theo*".

![GREEN-DESKTOP](assets/fr/25.webp)

Xác minh một lần nữa rằng địa chỉ, số lượng và phí là chính xác, sau đó nhấn vào "*Xác nhận giao dịch*".

![GREEN-DESKTOP](assets/fr/26.webp)

Đảm bảo tất cả các thông số giao dịch đều chính xác trên màn hình ví cứng của bạn, sau đó ký giao dịch sử dụng nó.

![GREEN-DESKTOP](assets/fr/27.webp)

Một khi giao dịch được ký từ ví cứng, Green tự động phát sóng nó trên mạng Bitcoin. Giao dịch của bạn sau đó sẽ xuất hiện trên bảng điều khiển của ví Bitcoin của bạn, chờ xác nhận.

![GREEN-DESKTOP](assets/fr/28.webp)

Và đó là tất cả, bạn giờ đã biết cách dễ dàng thiết lập phần mềm Blockstream Green để quản lý ví Bitcoin của mình trên một ví cứng.
Nếu bạn thấy hướng dẫn này hữu ích, tôi sẽ rất biết ơn nếu bạn có thể để lại một lượt thích phía dưới. Đừng ngần ngại chia sẻ bài viết này trên các mạng xã hội của bạn. Cảm ơn bạn rất nhiều!
Tôi cũng khuyên bạn nên xem hướng dẫn đầy đủ này về ứng dụng di động Blockstream Green để thiết lập một ví nóng:

https://planb.network/tutorials/wallet/blockstream-green