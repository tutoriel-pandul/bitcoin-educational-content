---
name: Blockstream Green - Di động
description: Cài đặt ví phần mềm trên điện thoại di động
---
![cover](assets/cover.webp)

Ví phần mềm là một ứng dụng được cài đặt trên máy tính, điện thoại thông minh, hoặc bất kỳ thiết bị nào khác có kết nối Internet, cho phép quản lý và bảo mật chìa khóa ví Bitcoin của người dùng. Khác với ví cứng, loại ví "nóng" này hoạt động trong môi trường có thể tiếp xúc với các cuộc tấn công mạng, làm tăng nguy cơ bị hack và mất cắp.

Ví phần mềm nên được sử dụng để quản lý số lượng bitcoins hợp lý, đặc biệt là cho các giao dịch hàng ngày. Đây cũng có thể là một lựa chọn thú vị cho những người có danh mục Bitcoin hạn chế, đối với họ việc đầu tư vào một ví cứng có thể cảm thấy không cân xứng. Tuy nhiên, việc tiếp xúc liên tục với Internet khiến chúng kém an toàn hơn để lưu trữ tiết kiệm dài hạn hoặc số tiền lớn. Đối với những trường hợp này, nên chọn các giải pháp an toàn hơn, như ví cứng.

Trong hướng dẫn này, tôi sẽ giới thiệu với bạn một trong những giải pháp ví phần mềm di động tốt nhất: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

Nếu bạn quan tâm đến việc học cách sử dụng Blockstream Green trên máy tính, vui lòng tham khảo hướng dẫn khác:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Giới thiệu về Blockstream Green

Blockstream Green là một ví phần mềm có sẵn trên cả di động và máy tính. Trước đây được biết đến với tên *Green Address*, ví này trở thành một dự án của Blockstream sau khi được mua lại vào năm 2016.

Green là một ứng dụng đặc biệt dễ sử dụng, làm cho nó trở nên thú vị đối với người mới bắt đầu. Nó cung cấp tất cả các tính năng cần thiết của một ví Bitcoin tốt, bao gồm RBF (*Replace-by-Fee*), tùy chọn kết nối qua Tor, khả năng kết nối với node của riêng bạn, tùy chọn SPV (*Simple Payment Verification*), gắn nhãn, và kiểm soát coin.

Blockstream Green cũng hỗ trợ mạng Liquid, một sidechain của Bitcoin được phát triển bởi Blockstream để thực hiện các giao dịch nhanh chóng và bảo mật bên ngoài blockchain chính. Hướng dẫn này chỉ tập trung vào Bitcoin, nhưng một hướng dẫn trong tương lai sẽ đề cập đến việc sử dụng Liquid.

## Cài đặt và Thiết lập Ứng dụng Blockstream Green

Bước đầu tiên tự nhiên là tải xuống ứng dụng Green. Truy cập cửa hàng ứng dụng của bạn:
- [Cho Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Cho Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

Đối với người dùng Android, bạn cũng có tùy chọn cài đặt ứng dụng qua tệp `.apk` [có sẵn trên GitHub của Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN](assets/fr/03.webp)
Khởi chạy ứng dụng, sau đó đánh dấu vào ô "*Tôi chấp nhận các điều kiện...*".
![GREEN](assets/fr/04.webp)

Khi bạn mở Green lần đầu tiên, màn hình chính xuất hiện mà không có ví nào được cấu hình. Sau này, nếu bạn tạo hoặc nhập ví, chúng sẽ xuất hiện trong giao diện này. Trước khi chuyển sang tạo ví, tôi khuyên bạn nên điều chỉnh cài đặt ứng dụng theo mong đợi của mình. Nhấp vào "*Cài đặt Ứng dụng*".

![GREEN](assets/fr/05.webp)

Tùy chọn "*Tăng cường Quyền riêng tư*", chỉ có sẵn trên Android, cải thiện quyền riêng tư bằng cách vô hiệu hóa chụp màn hình và ẩn xem trước ứng dụng. Nó cũng tự động khóa quyền truy cập vào ứng dụng ngay khi điện thoại của bạn bị khóa, làm cho dữ liệu của bạn khó bị phơi bày hơn.

![GREEN](assets/fr/06.webp)
Dành cho những ai muốn tăng cường quyền riêng tư, ứng dụng cung cấp lựa chọn định tuyến lưu lượng truy cập của bạn qua Tor, một mạng lưới mã hóa tất cả các kết nối của bạn và làm cho các hoạt động của bạn khó theo dõi. Mặc dù tùy chọn này có thể làm chậm hiệu suất của ứng dụng, nhưng nó được khuyến nghị cao để bảo vệ quyền riêng tư của bạn, đặc biệt là nếu bạn không sử dụng full node của riêng mình.
![GREEN](assets/fr/07.webp)

Đối với những người dùng có full node của riêng mình, Green Wallet cung cấp khả năng kết nối với nó qua một máy chủ Electrum, đảm bảo quyền kiểm soát đầy đủ thông tin mạng Bitcoin và phát sóng giao dịch.

![GREEN](assets/fr/08.webp)

Một tính năng thay thế khác là tùy chọn "*SPV Verification*", cho phép xác minh trực tiếp một số dữ liệu blockchain, giảm bớt sự cần thiết phải tin tưởng vào node Blockstream mặc định, mặc dù phương pháp này không cung cấp tất cả các bảo đảm của một full node.

![GREEN](assets/fr/09.webp)

Sau khi điều chỉnh các cài đặt này theo nhu cầu của bạn, nhấn vào nút "*Save*" và khởi động lại ứng dụng.

![GREEN](assets/fr/10.webp)

## Tạo một Ví Bitcoin trên Blockstream Green

Bây giờ bạn đã sẵn sàng để tạo một ví Bitcoin. Nhấn vào nút "*Get Started*".

![GREEN](assets/fr/11.webp)

Bạn có sự lựa chọn giữa việc tạo một ví phần mềm cục bộ hoặc quản lý một ví lạnh qua một ví cứng. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc tạo một ví nóng, vì vậy bạn sẽ cần chọn tùy chọn "*On This Device*". Trong một hướng dẫn tương lai, tôi sẽ chỉ bạn cách sử dụng tùy chọn khác.

Tùy chọn "*Watch-only*", mặt khác, cho phép bạn nhập một khóa công khai mở rộng (`xpub`) để xem các giao dịch của một ví mà không thể chi tiêu các quỹ liên quan, điều này thuận tiện cho việc giám sát một ví trên một ví cứng, chẳng hạn.

![GREEN](assets/fr/12.webp)
Sau đó, bạn có thể chọn khôi phục một ví Bitcoin đã tồn tại hoặc tạo một cái mới. Với mục đích của hướng dẫn này, chúng tôi sẽ tạo một ví mới. Tuy nhiên, nếu bạn cần tái tạo một ví Bitcoin đã tồn tại từ cụm từ ghi nhớ của nó, ví dụ, do mất ví cứng của bạn, bạn sẽ cần chọn tùy chọn thứ hai.
![GREEN](assets/fr/13.webp)

Sau đó, bạn có sự lựa chọn giữa một cụm từ ghi nhớ 12 từ hoặc 24 từ. Cụm từ này sẽ cho phép bạn khôi phục quyền truy cập vào ví của mình từ bất kỳ phần mềm tương thích nào trong trường hợp có vấn đề với điện thoại của bạn. Hiện tại, lựa chọn một cụm từ 24 từ không cung cấp nhiều bảo mật hơn so với một cụm từ 12 từ. Do đó, tôi khuyên bạn nên chọn một **cụm từ ghi nhớ 12 từ**.

Green sau đó sẽ cung cấp cho bạn cụm từ ghi nhớ của mình. Trước khi tiếp tục, hãy chắc chắn rằng bạn không bị quan sát. Nhấn vào "*Show recovery phrase*" để hiển thị nó trên màn hình.

![GREEN](assets/fr/14.webp)

**Cụm từ ghi nhớ này cung cấp quyền truy cập đầy đủ và không giới hạn vào tất cả bitcoins của bạn.** Bất kỳ ai sở hữu cụm từ này có thể ăn cắp quỹ của bạn, ngay cả khi không có quyền truy cập vật lý vào điện thoại của bạn.

Nó cho phép bạn khôi phục quyền truy cập vào bitcoins của bạn trong trường hợp mất mát, trộm cắp, hoặc hỏng hóc điện thoại. Do đó, việc lưu trữ nó cẩn thận **trên một phương tiện vật lý (không phải kỹ thuật số)** và bảo quản nó ở một nơi an toàn là rất quan trọng. Bạn có thể ghi nó ra một tờ giấy, hoặc để đảm bảo an toàn hơn, nếu ví này quan trọng, tôi khuyên bạn nên khắc nó trên một phương tiện bằng thép không gỉ để bảo vệ khỏi rủi ro của hỏa hoạn, lũ lụt, hoặc sụp đổ (đối với một ví nóng nhằm bảo vệ một lượng nhỏ bitcoins, một bản sao giấy đơn giản có lẽ là đủ).
*Rõ ràng, bạn không bao giờ nên chia sẻ những từ này trên internet, trái ngược với những gì tôi đang làm trong hướng dẫn này. Ví dụ này chỉ được sử dụng trên Testnet và sẽ được xóa vào cuối hướng dẫn.*
![GREEN](assets/fr/15.webp)

Sau khi ghi chú cụm từ ghi nhớ của bạn một cách chính xác trên một phương tiện vật lý, nhấp vào "*Tiếp tục*". Ví Green sau đó sẽ yêu cầu bạn xác nhận một số từ trong cụm từ của bạn để kiểm tra xem bạn đã ghi chép chúng một cách chính xác hay không. Điền vào chỗ trống với những từ còn thiếu.

![GREEN](assets/fr/16.webp)

Chọn mã PIN cho thiết bị của bạn, sẽ được sử dụng để mở khóa ví Green của bạn. Do đó, đây là một biện pháp bảo vệ chống lại việc truy cập vật lý không được phép. Mã PIN này không tham gia vào việc tạo ra các khóa mật mã của ví bạn. Do đó, ngay cả khi không có quyền truy cập vào mã PIN này, việc sở hữu cụm từ ghi nhớ 12 hoặc 24 từ của bạn sẽ cho phép bạn lấy lại quyền truy cập vào bitcoin của mình.
Được khuyến nghị chọn một mã PIN 6 chữ số càng ngẫu nhiên càng tốt. Ngoài ra, hãy chắc chắn sao lưu mã này để bạn không quên nó, nếu không, bạn sẽ buộc phải khôi phục ví của mình sử dụng cụm từ ghi nhớ. Sau đó, bạn có thể thêm tùy chọn khóa sinh trắc học để tránh phải nhập mã PIN mỗi khi sử dụng. Nói chung, sinh trắc học kém an toàn hơn nhiều so với chính mã PIN. Do đó, mặc định, tôi khuyên bạn không nên thiết lập tùy chọn mở khóa này.
![GREEN](assets/fr/17.webp)

Nhập lại mã PIN một lần nữa để xác nhận.

![GREEN](assets/fr/18.webp)

Chờ đợi ví của bạn được tạo, sau đó nhấp vào nút "*Tạo một tài khoản*".

![GREEN](assets/fr/19.webp)

Bạn sau đó có sự lựa chọn giữa một ví chữ ký đơn tiêu chuẩn, mà chúng tôi sẽ sử dụng trong hướng dẫn này, hoặc một ví được bảo vệ bởi xác thực hai yếu tố (2FA).

![GREEN](assets/fr/20.webp)

Tùy chọn 2FA trên Green tạo ra một ví đa chữ ký 2/2, một khóa trong số đó được giữ bởi Blockstream. Điều này có nghĩa là để thực hiện một giao dịch, cả hai khóa đều được yêu cầu: một khóa cục bộ được bảo vệ bởi mã PIN trên điện thoại của bạn, và một khóa từ xa được bảo mật bởi 2FA trên máy chủ của Blockstream. Trong trường hợp mất quyền truy cập vào 2FA hoặc dịch vụ của Blockstream không khả dụng, các cơ chế khôi phục dựa trên kịch bản khóa thời gian đảm bảo khả năng khôi phục độc lập quỹ của bạn. Mặc dù cài đặt này giảm đáng kể nguy cơ bitcoin của bạn bị đánh cắp, nhưng nó phức tạp hơn để quản lý và phụ thuộc một phần vào Blockstream. Đối với hướng dẫn này, chúng tôi sẽ chọn một ví chữ ký đơn cổ điển, với các khóa được lưu trữ cục bộ trên điện thoại.

Và bạn đã tạo thành công ví Bitcoin của mình sử dụng ứng dụng Green!

![GREEN](assets/fr/21.webp)

Trước khi nhận bitcoin đầu tiên vào ví của bạn, **tôi rất khuyên bạn nên thực hiện một bài kiểm tra khôi phục thử nghiệm**. Ghi chú thông tin tham chiếu, như xpub của bạn hoặc địa chỉ nhận đầu tiên, sau đó xóa ví của bạn trên ứng dụng Green trong khi nó vẫn trống. Tiếp theo, thử khôi phục ví của bạn trên Green sử dụng bản sao lưu giấy của bạn. Kiểm tra xem thông tin chứng thực được tạo ra sau khi khôi phục có khớp với thông tin bạn đã ghi chú ban đầu hay không. Nếu đúng như vậy, bạn có thể yên tâm rằng bản sao lưu giấy của bạn là đáng tin cậy. Để tìm hiểu thêm về cách thực hiện một bài kiểm tra khôi phục, tôi khuyên bạn nên tham khảo hướng dẫn khác này:

https://planb.network/tutorials/wallet/recovery-test

## Cài đặt ví của bạn trên Blockstream Green
Nếu bạn muốn tùy chỉnh danh mục đầu tư của mình, nhấp vào ba chấm nhỏ ở góc trên bên phải.
![GREEN](assets/fr/22.webp)
Tùy chọn "*Đổi tên*" cho phép bạn tùy chỉnh tên của danh mục đầu tư, điều này rất hữu ích nếu bạn quản lý nhiều danh mục đầu tư trên cùng một ứng dụng.
![GREEN](assets/fr/23.webp)

Menu "*Đơn vị*" cho phép bạn thay đổi đơn vị cơ bản của danh mục đầu tư. Ví dụ, bạn có thể chọn hiển thị nó bằng satoshis thay vì bitcoins.

![GREEN](assets/fr/24.webp)

Menu "*Cài đặt*" cung cấp quyền truy cập vào các tùy chọn khác nhau của ví Bitcoin của bạn.

![GREEN](assets/fr/25.webp)

Ở đây, ví dụ, bạn sẽ tìm thấy khóa công khai mở rộng của mình và *mô tả* của nó, hữu ích nếu bạn dự định thiết lập một ví chỉ xem từ ví này.

![GREEN](assets/fr/26.webp)

Bạn cũng có thể thay đổi mã PIN của ví và kích hoạt đăng nhập sinh trắc học.

![GREEN](assets/fr/27.webp)

## Sử dụng Blockstream Green

Bây giờ ví Bitcoin của bạn đã được thiết lập, bạn đã sẵn sàng để nhận sats đầu tiên của mình! Để làm điều này, chỉ cần nhấp vào nút "*Nhận*".

![GREEN](assets/fr/28.webp)

Green sau đó sẽ hiển thị địa chỉ nhận trống đầu tiên của ví bạn. Bạn có thể quét mã QR liên kết hoặc sao chép địa chỉ trực tiếp để gửi bitcoins đến nó. Loại địa chỉ này không chỉ định số lượng cần gửi bởi người thanh toán. Tuy nhiên, bạn có thể tạo một địa chỉ yêu cầu một số lượng cụ thể, bằng cách nhấp vào ba chấm nhỏ ở góc trên bên phải, sau đó chọn "*Yêu cầu Số lượng*", và nhập số lượng mong muốn.

Vì bạn đang sử dụng tài khoản Segwit v0 (BIP84), địa chỉ của bạn sẽ bắt đầu với `bc1q...`. Trong ví dụ của tôi, tôi đang sử dụng ví Testnet, vì vậy tiền tố hơi khác.

![GREEN](assets/fr/29.webp)

Khi giao dịch được phát sóng trên mạng, nó sẽ xuất hiện trong ví của bạn.

![GREEN](assets/fr/30.webp)

Chờ đợi để nhận đủ xác nhận để coi giao dịch là cuối cùng.

![GREEN](assets/fr/31.webp)

Với bitcoins trong ví của bạn, bây giờ bạn cũng có thể gửi chúng. Nhấp vào "*Gửi*".

![GREEN](assets/fr/32.webp)

Trên trang tiếp theo, nhập địa chỉ của người nhận. Bạn có thể nhập nó thủ công hoặc quét mã QR.

![GREEN](assets/fr/33.webp)

Chọn số lượng thanh toán.

![GREEN](assets/fr/34.webp)
Ở cuối màn hình, bạn có thể chọn mức phí cho giao dịch này. Bạn có tùy chọn tuân theo khuyến nghị của ứng dụng hoặc tùy chỉnh phí của mình. Phí cao hơn so với các giao dịch đang chờ khác, giao dịch của bạn sẽ được xử lý nhanh hơn. Để hiểu về thị trường phí, bạn có thể truy cập [Mempool.space](https://mempool.space/) trong phần "*Phí Giao Dịch*".
![GREEN](assets/fr/35.webp)

Nhấp vào "*Tiếp theo*" để truy cập màn hình tóm tắt giao dịch của bạn. Xác minh địa chỉ, số lượng và phí có chính xác không.

![GREEN](assets/fr/36.webp)

Nếu mọi thứ đều đúng như bạn mong đợi, kéo nút xanh ở cuối màn hình sang phải để ký và phát sóng giao dịch trên mạng Bitcoin.

![GREEN](assets/fr/37.webp)

Giao dịch của bạn giờ đây sẽ xuất hiện trên bảng điều khiển của ví Bitcoin chờ xác nhận.

![GREEN](assets/fr/38.webp)
*Hướng dẫn này dựa trên [phiên bản gốc thuộc về Bitstack](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet) được viết bởi Loïc Morel. Bitstack là một neo-bank Bitcoin của Pháp, cung cấp khả năng tiết kiệm bằng bitcoin, thông qua DCA (Dollar Cost Averaging) hoặc qua hệ thống làm tròn tự động cho các chi tiêu hàng ngày.*