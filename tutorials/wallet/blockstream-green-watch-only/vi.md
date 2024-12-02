---
name: Blockstream Green - Chỉ Xem
description: Cài đặt ví chỉ xem
---
![cover](assets/cover.webp)

Trong hướng dẫn này, bạn sẽ học cách dễ dàng thiết lập một ví chỉ xem trên điện thoại sử dụng ứng dụng Blockstream Green.

## Ví Chỉ Xem là gì?

Ví chỉ xem, hay còn gọi là "ví chỉ xem," là một loại phần mềm được thiết kế để cho phép người dùng quan sát các giao dịch liên quan đến một hoặc nhiều khóa công khai Bitcoin cụ thể, mà không cần truy cập vào các khóa riêng tương ứng.

Loại ứng dụng này chỉ giữ lại dữ liệu cần thiết để giám sát một ví Bitcoin, bao gồm việc xem số dư và lịch sử giao dịch, nhưng nó không có quyền truy cập vào các khóa riêng. Do đó, việc chi tiêu bitcoin trong ví trên ứng dụng chỉ xem là không thể.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Chức năng chỉ xem thường được sử dụng kết hợp với một ví cứng. Ví cứng cho phép lưu trữ an toàn các khóa riêng của ví trên một thiết bị không kết nối internet, có bề mặt tấn công tối thiểu, do đó cô lập các khóa riêng khỏi môi trường có thể bị tấn công. Ngược lại, ứng dụng chỉ xem chỉ lưu trữ khóa công khai mở rộng (`xpub`, `zpub`, v.v.) của ví Bitcoin. Khóa cha này không cho phép phát hiện các khóa riêng liên quan và do đó, không cho phép chi tiêu bitcoin. Tuy nhiên, nó cho phép tạo ra các khóa công khai con và địa chỉ nhận. Với kiến thức về các địa chỉ của ví được bảo vệ bởi ví cứng, ứng dụng chỉ xem có thể theo dõi các giao dịch này trên mạng Bitcoin, cung cấp cho người dùng khả năng giám sát số dư của họ và tạo địa chỉ nhận mới, mà không cần phải kết nối ví cứng mỗi lần.

Trong hướng dẫn này, tôi đề xuất khám phá một trong những giải pháp ví chỉ xem phổ biến nhất trên di động: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Giới thiệu về Blockstream Green

Blockstream Green là phần mềm có sẵn trên di động và máy tính. Trước đây được biết đến với tên Green Address, ví này trở thành một dự án của Blockstream sau khi được mua lại vào năm 2016.

Green là một ứng dụng rất dễ sử dụng, làm cho nó đặc biệt phù hợp với người mới bắt đầu. Nó cung cấp các tính năng đa dạng, như quản lý ví nóng, ví cứng, cũng như ví trên chuỗi phụ Liquid.

Trong hướng dẫn này, chúng tôi sẽ chỉ tập trung vào việc tạo một ví chỉ xem. Để khám phá các ứng dụng khác của Green, tôi mời bạn tham khảo các hướng dẫn chuyên dụng khác của chúng tôi:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Cài đặt và Thiết lập Ứng dụng Blockstream Green
Bước đầu tiên tự nhiên là tải xuống ứng dụng Green. Truy cập cửa hàng ứng dụng của bạn:
- [Cho Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Cho Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

Đối với người dùng Android, bạn cũng có tùy chọn cài đặt ứng dụng qua tệp `.apk` [có sẵn trên GitHub của Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Khởi chạy ứng dụng, sau đó đánh dấu vào ô "*Tôi chấp nhận các điều khoản...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)
Khi bạn mở Green lần đầu tiên, màn hình chính hiện lên mà không có ví nào được cấu hình. Sau này, nếu bạn tạo hoặc nhập ví, chúng sẽ xuất hiện trong giao diện này. Trước khi tiếp tục tạo ví, tôi khuyên bạn nên điều chỉnh cài đặt của ứng dụng theo mong đợi của bạn. Nhấp vào "*Cài Đặt Ứng Dụng*".
![GREEN-WATCH-ONLY](assets/fr/06.webp)

Tùy chọn "*Tăng Cường Quyền Riêng Tư*", chỉ có sẵn trên Android, cải thiện quyền riêng tư bằng cách vô hiệu hóa chức năng chụp màn hình và ẩn xem trước ứng dụng. Nó cũng tự động khóa quyền truy cập vào ứng dụng ngay khi điện thoại của bạn bị khóa, làm cho dữ liệu của bạn khó bị phơi bày hơn.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

Đối với những người muốn tăng cường quyền riêng tư của mình, ứng dụng cung cấp lựa chọn định tuyến lưu lượng truy cập của bạn qua Tor, một mạng lưới mã hóa tất cả các kết nối của bạn và làm cho các hoạt động của bạn khó theo dõi. Mặc dù tùy chọn này có thể làm chậm hiệu suất của ứng dụng một chút, nhưng nó được khuyến nghị cao để bảo vệ quyền riêng tư của bạn, đặc biệt nếu bạn không sử dụng full node của riêng mình.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

Đối với người dùng có full node của riêng mình, Green Wallet cung cấp khả năng kết nối với nó qua một máy chủ Electrum, đảm bảo kiểm soát đầy đủ thông tin mạng lưới Bitcoin và phát sóng giao dịch.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Một tính năng thay thế khác là tùy chọn "*Xác Minh SPV*", cho phép xác minh trực tiếp một số dữ liệu blockchain, do đó giảm bớt sự cần thiết phải tin tưởng vào node mặc định của Blockstream, mặc dù phương pháp này không cung cấp tất cả các bảo đảm của một full node.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Sau khi điều chỉnh các cài đặt này theo nhu cầu của bạn, nhấp vào nút "*Lưu*" và khởi động lại ứng dụng.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Tạo một ví chỉ xem trên Blockstream Green
Bây giờ bạn đã sẵn sàng để tạo một ví chỉ xem. Nhấp vào nút "*Bắt Đầu*".
![GREEN-WATCH-ONLY](assets/fr/12.webp)

Bạn sẽ có sự lựa chọn giữa nhiều loại ví. Đối với hướng dẫn này, chúng tôi muốn tạo một ví chỉ xem, vì vậy hãy nhấp vào nút tương ứng.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Chọn tùy chọn "*Chữ Ký Đơn*".

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Sau đó chọn "*Bitcoin*". Về phần mình, tôi thực hiện hướng dẫn này trên một ví testnet, nhưng quy trình vẫn giống nhau trên mainnet.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

Bạn sẽ được yêu cầu cung cấp hoặc một khóa công khai mở rộng (`xpub`, `zpub`, v.v.), hoặc một mô tả script đầu ra.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

Bạn sẽ cần lấy thông tin này từ ví mà bạn muốn theo dõi qua ví chỉ xem của mình. Khóa công khai mở rộng không nhạy cảm về mặt bảo mật, vì nó không cho phép truy cập vào khóa riêng, nhưng nó nhạy cảm với quyền riêng tư của bạn, vì nó tiết lộ tất cả các khóa công khai của bạn và do đó tất cả các giao dịch Bitcoin của bạn.

Hãy tưởng tượng bạn đang sử dụng Sparrow Wallet để quản lý ví của mình trên một ví cứng, bạn sẽ tìm thấy thông tin này trong mục "*Cài Đặt*". Việc tìm kiếm thông tin này sẽ phụ thuộc vào phần mềm quản lý ví bạn đang sử dụng, nhưng nói chung là được tìm thấy trong cài đặt.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Sao chép khóa công khai mở rộng của bạn và nhập nó vào ứng dụng Green, sau đó nhấp vào "*Kết Nối*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

Sau đó, bạn sẽ có thể xem số dư liên kết với khóa này cũng như lịch sử giao dịch.
![GREEN-WATCH-ONLY](assets/fr/19.webp)
Bằng cách nhấp vào "*Nhận*", bạn có thể tạo một địa chỉ nhận để nhận bitcoin vào ví cứng của mình. Tuy nhiên, tôi khuyên bạn không nên sử dụng tùy chọn này mà không trước tiên xác minh trên màn hình của ví cứng rằng nó giữ khóa riêng tư liên kết với địa chỉ được tạo, trước khi sử dụng nó để khóa bitcoin. Đây là một thực hành tốt cần tuân theo.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

Tùy chọn "*Quét*" cho phép bạn nhập thủ công một khóa riêng tư để chi tiêu tiền trực tiếp từ ứng dụng Green của bạn. Trừ trong những trường hợp cực kỳ cụ thể, tôi khuyên bạn không nên sử dụng chức năng này, vì nó đòi hỏi phải tiết lộ khóa riêng tư của bạn trên điện thoại, điều này dễ bị tấn công mạng hơn nhiều so với ví cứng của bạn.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
Và đó là tất cả, bạn giờ đã biết cách dễ dàng thiết lập một ví chỉ xem trên điện thoại thông minh của mình! Đây là một công cụ rất tiện lợi để theo dõi một ví trên ví cứng mà không cần phải kết nối và mở khóa mỗi lần.

Nếu bạn thấy hướng dẫn này hữu ích, tôi sẽ rất biết ơn nếu bạn có thể để lại một lượt thích phía dưới. Đừng ngần ngại chia sẻ bài viết này trên các mạng xã hội của bạn. Cảm ơn bạn rất nhiều!

Tôi cũng khuyên bạn nên xem hướng dẫn đầy đủ này về ứng dụng Blockstream Green để thiết lập một ví nóng:

https://planb.network/tutorials/wallet/blockstream-green