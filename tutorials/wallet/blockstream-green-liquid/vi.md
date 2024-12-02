---
name: Blockstream Green - Liquid
description: Cài đặt ví trên sidechain Liquid Network
---
![cover](assets/cover.webp)
Giao thức Bitcoin có những hạn chế kỹ thuật cố ý giúp duy trì sự phân quyền của mạng và đảm bảo sự phân phối an ninh cho tất cả người dùng. Tuy nhiên, những giới hạn này đôi khi làm người dùng cảm thấy bất tiện, đặc biệt là trong những thời điểm tắc nghẽn do lượng giao dịch đồng thời cao. Cuộc tranh luận về khả năng mở rộng của Bitcoin đã chia rẽ cộng đồng từ lâu, đặc biệt là trong suốt Cuộc chiến Blocksize. Kể từ đó, cộng đồng Bitcoin rộng lớn đã nhận ra rằng việc đảm bảo khả năng mở rộng phải thông qua các giải pháp ngoài chuỗi, trên các hệ thống lớp thứ hai. Trong số các giải pháp này, sidechain vẫn còn tương đối mới mẻ và ít được sử dụng so với các hệ thống khác như Lightning Network.

Sidechain là một blockchain độc lập hoạt động song song với blockchain chính của Bitcoin. Nó sử dụng bitcoin như một đơn vị tài khoản thông qua một cơ chế gọi là "*two-way peg*". Hệ thống này cho phép khóa bitcoin trên chuỗi chính để sao chép giá trị của chúng trên sidechain, nơi chúng lưu thông dưới dạng token được bảo đảm bởi bitcoin gốc. Những token này thường duy trì một giá trị tương đương với bitcoin được khóa trên chuỗi chính, và quá trình này có thể được đảo ngược để thu hồi các quỹ trên Bitcoin.

Mục tiêu của sidechain là cung cấp các chức năng bổ sung hoặc cải tiến kỹ thuật, như giao dịch nhanh hơn, phí thấp hơn, hoặc hỗ trợ cho hợp đồng thông minh. Những đổi mới này không phải lúc nào cũng có thể được triển khai trực tiếp trên blockchain Bitcoin mà không làm ảnh hưởng đến sự phân quyền hoặc an ninh của nó. Sidechain do đó cho phép thử nghiệm và khám phá các giải pháp mới trong khi vẫn bảo toàn tính toàn vẹn của Bitcoin. Tuy nhiên, những giao thức này thường đòi hỏi những sự thỏa hiệp, đặc biệt là về mặt phân quyền và an ninh, tùy thuộc vào mô hình quản trị và cơ chế đồng thuận được chọn.

Ngày nay, sidechain được biết đến nhiều nhất có lẽ là Liquid. Trong hướng dẫn này, tôi sẽ đầu tiên giới thiệu với bạn Liquid là gì, sau đó hướng dẫn bạn cách bắt đầu sử dụng nó một cách dễ dàng thông qua ứng dụng Blockstream Green, để tận dụng các lợi ích của nó.

![LIQUID GREEN](assets/fr/01.webp)

## Liquid Network là gì?

Liquid là một sidechain liên kết được xây dựng trên Bitcoin, phát triển bởi Blockstream, nhằm cải thiện tốc độ, quyền riêng tư, và chức năng của các giao dịch. Nó sử dụng một cơ chế neo hai chiều dựa trên một liên minh để khóa bitcoin trên chuỗi chính và tạo ra, đổi lại, Liquid-bitcoins (L-BTC), các token lưu thông trên Liquid trong khi vẫn được bảo đảm bởi bitcoin gốc.

![LIQUID GREEN](assets/fr/02.webp)
Mạng Liquid dựa trên một liên minh các bên tham gia, bao gồm các thực thể được công nhận từ hệ sinh thái Bitcoin, những người này xác nhận các khối và quản lý việc neo hai chiều. Ngoài L-BTC, Liquid còn cho phép phát hành các tài sản số khác, như stablecoins hoặc các loại tiền điện tử khác.
![LIQUID GREEN](assets/fr/03.webp)

## Giới thiệu về Blockstream Green

Blockstream Green là một ví phần mềm có sẵn trên di động và máy tính để bàn. Trước đây được biết đến với tên gọi *Green Address*, ví này trở thành một dự án của Blockstream sau khi được mua lại vào năm 2016.

Green là một ứng dụng đặc biệt dễ sử dụng, làm cho nó thú vị đối với người mới bắt đầu. Nó cung cấp tất cả các tính năng cần thiết của một ví Bitcoin tốt, bao gồm RBF (*Replace-by-Fee*), tùy chọn kết nối qua Tor, khả năng kết nối với node của riêng bạn, tùy chọn SPV (*Simple Payment Verification*), gắn nhãn, và kiểm soát coin.

Blockstream Green cũng hỗ trợ mạng Liquid, và đó là điều chúng ta sẽ khám phá trong hướng dẫn này. Nếu bạn muốn sử dụng Green cho các ứng dụng khác, tôi cũng khuyên bạn nên tham khảo các hướng dẫn khác:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## Cài Đặt và Thiết Lập Ứng Dụng Blockstream Green

Bước đầu tiên tự nhiên là tải xuống ứng dụng Green. Hãy truy cập cửa hàng ứng dụng của bạn:
- [Cho Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet) ;
- [Cho Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

Đối với người dùng Android, bạn cũng có tùy chọn cài đặt ứng dụng qua tệp `.apk` [có sẵn trên GitHub của Blockstream](https://github.com/Blockstream/green_android/releases).

![LIQUID GREEN](assets/fr/05.webp)

Khởi chạy ứng dụng, sau đó đánh dấu vào ô "*Tôi chấp nhận các điều khoản...*".

![LIQUID GREEN](assets/fr/06.webp)

Khi bạn mở Green lần đầu tiên, màn hình chính hiện ra mà không có ví nào được cấu hình. Sau này, nếu bạn tạo hoặc nhập ví, chúng sẽ xuất hiện trong giao diện này. Trước khi chuyển sang tạo ví, tôi khuyên bạn nên điều chỉnh các cài đặt ứng dụng theo mong đợi của bạn. Nhấp vào "*Cài Đặt Ứng Dụng*".

![LIQUID GREEN](assets/fr/07.webp)

Tùy chọn "*Tăng Cường Quyền Riêng Tư*", chỉ có sẵn trên Android, cải thiện quyền riêng tư bằng cách vô hiệu hóa chụp màn hình và ẩn xem trước ứng dụng. Nó cũng tự động khóa quyền truy cập vào ứng dụng ngay khi điện thoại của bạn bị khóa, làm cho dữ liệu của bạn khó bị phơi bày hơn.
![LIQUID GREEN](assets/fr/08.webp)
Đối với những người muốn tăng cường quyền riêng tư, ứng dụng cung cấp tùy chọn định tuyến lưu lượng truy cập của bạn qua Tor, một mạng lưới mã hóa tất cả các kết nối của bạn và làm cho các hoạt động của bạn khó theo dõi. Mặc dù tùy chọn này có thể làm chậm hiệu suất của ứng dụng một chút, nhưng nó được khuyến nghị cao để bảo vệ quyền riêng tư của bạn, đặc biệt nếu bạn không sử dụng full node của riêng mình.

![LIQUID GREEN](assets/fr/09.webp)

Đối với người dùng có full node của riêng mình, Ví Green cho phép bạn kết nối với nó qua một máy chủ Electrum, đảm bảo kiểm soát đầy đủ thông tin mạng Bitcoin và phát sóng giao dịch. Tuy nhiên, tính năng này chỉ liên quan đến ví Bitcoin truyền thống, vì vậy bạn không cần nó nếu bạn đang sử dụng Liquid.

![LIQUID GREEN](assets/fr/10.webp)

Một tính năng thay thế khác là tùy chọn "*Xác Minh SPV*", cho phép xác minh trực tiếp một số dữ liệu blockchain, do đó giảm bớt sự cần thiết phải tin tưởng vào node mặc định của Blockstream, mặc dù phương pháp này không cung cấp tất cả các đảm bảo của một full node. Một lần nữa, điều này chỉ liên quan đến ví Bitcoin onchain của bạn, và không phải Liquid.

![LIQUID GREEN](assets/fr/11.webp)

Sau khi điều chỉnh các cài đặt này theo nhu cầu của bạn, nhấp vào nút "*Lưu*" và khởi động lại ứng dụng.

![LIQUID GREEN](assets/fr/12.webp)

## Tạo Ví Liquid trên Blockstream Green

Bây giờ bạn đã sẵn sàng để tạo một ví Liquid. Nhấp vào nút "*Bắt Đầu*".

![LIQUID GREEN](assets/fr/13.webp)

Bạn có sự lựa chọn giữa việc tạo một ví phần mềm cục bộ hoặc quản lý một ví lạnh qua một ví cứng. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc tạo một ví nóng trên Liquid, vì vậy bạn sẽ cần chọn tùy chọn "*Trên Thiết Bị Này*". Bạn cũng có thể sử dụng một ví cứng tương thích, như Blockstream Jade, để bảo vệ ví Liquid của mình.

![LIQUID GREEN](assets/fr/14.webp)
Sau đó, bạn có thể chọn khôi phục một ví Bitcoin đã có hoặc tạo một ví mới. Với mục đích của hướng dẫn này, chúng ta sẽ tạo một ví mới. Tuy nhiên, nếu bạn cần tái tạo một ví Liquid đã có từ cụm từ ghi nhớ của nó, ví dụ, do mất ví cứng của bạn, bạn sẽ cần chọn lựa chọn thứ hai.
![LIQUID GREEN](assets/fr/15.webp)

Sau đó, bạn có sự lựa chọn giữa cụm từ ghi nhớ 12 từ hoặc 24 từ. Cụm từ này sẽ cho phép bạn khôi phục quyền truy cập vào ví của mình từ bất kỳ phần mềm tương thích nào trong trường hợp có vấn đề với điện thoại của bạn. Hiện tại, việc chọn cụm từ 24 từ không cung cấp nhiều an ninh hơn so với cụm từ 12 từ. Do đó, tôi khuyên bạn nên chọn cụm từ ghi nhớ **12 từ**.
Green sau đó sẽ cung cấp cho bạn cụm từ ghi nhớ của mình. Trước khi tiếp tục, hãy đảm bảo bạn không bị quan sát. Nhấp vào "*Hiển thị cụm từ khôi phục*" để hiển thị nó trên màn hình.
![LIQUID GREEN](assets/fr/16.webp)

**Cụm từ ghi nhớ này cho phép truy cập đầy đủ và không bị hạn chế vào tất cả bitcoin của bạn.** Bất kỳ ai sở hữu cụm từ này có thể ăn cắp tiền của bạn, ngay cả khi không có quyền truy cập vật lý vào điện thoại của bạn.

Nó cho phép bạn khôi phục quyền truy cập vào bitcoin của mình trong trường hợp mất mát, trộm cắp, hoặc hư hại điện thoại. Do đó, việc lưu giữ cẩn thận nó **trên một phương tiện vật lý (không phải kỹ thuật số)** và lưu trữ nó ở một vị trí an toàn là rất quan trọng. Bạn có thể ghi nó ra một tờ giấy, hoặc để an toàn hơn, nếu ví này quan trọng, tôi khuyên bạn nên khắc nó trên một phương tiện bằng thép không gỉ để bảo vệ khỏi rủi ro của hỏa hoạn, lũ lụt, hoặc sụp đổ (đối với một ví nóng nhằm bảo vệ một lượng nhỏ bitcoin, một bản sao lưu giấy đơn giản có lẽ là đủ).

*Rõ ràng, bạn không bao giờ nên chia sẻ những từ này trên internet, trái ngược với những gì tôi đang làm trong hướng dẫn này. Ví dụ này chỉ được sử dụng trên Liquid Testnet và sẽ được xóa vào cuối hướng dẫn.*

![LIQUID GREEN](assets/fr/17.webp)

Sau khi ghi chính xác cụm từ ghi nhớ của bạn trên một phương tiện vật lý, nhấp vào "*Tiếp tục*". Ví Green sau đó sẽ yêu cầu bạn xác nhận một số từ từ cụm từ của bạn để kiểm tra xem bạn đã ghi chép chúng một cách chính xác hay không. Điền vào các ô trống với những từ còn thiếu.

![LIQUID GREEN](assets/fr/18.webp)

Chọn mã PIN cho thiết bị của bạn, sẽ được sử dụng để mở khóa ví Green của bạn. Do đó, đây là một biện pháp bảo vệ chống lại quyền truy cập vật lý không được phép. Mã PIN này không tham gia vào việc tạo ra các khóa mật mã của ví của bạn. Do đó, ngay cả khi không có quyền truy cập vào mã PIN này, việc sở hữu cụm từ ghi nhớ 12 hoặc 24 từ của bạn sẽ cho phép bạn lấy lại quyền truy cập vào bitcoin của mình.

Khuyến nghị chọn một mã PIN 6 chữ số càng ngẫu nhiên càng tốt. Ngoài ra, hãy chắc chắn lưu mã này để bạn không quên nó, nếu không, bạn sẽ buộc phải khôi phục ví của mình từ cụm từ ghi nhớ. Sau này, bạn có thể thêm tùy chọn khóa sinh trắc học để tránh nhập mã PIN mỗi khi sử dụng. Nói chung, sinh trắc học kém an toàn hơn chính mã PIN. Do đó, theo mặc định, tôi khuyên bạn không nên thiết lập tùy chọn mở khóa này.

![LIQUID GREEN](assets/fr/19.webp)

Nhập lại mã PIN một lần nữa để xác nhận.

![LIQUID GREEN](assets/fr/20.webp)
Đợi ví của bạn được tạo, sau đó nhấp vào nút "*Tạo một tài khoản*".
![LIQUID GREEN](assets/fr/21.webp)
Trong hộp "*Assets*", chọn "*Liquid Bitcoin*". Bạn có lựa chọn giữa ví đơn chữ ký tiêu chuẩn, mà chúng tôi sẽ sử dụng trong hướng dẫn này, hoặc một ví được bảo vệ bởi xác thực hai yếu tố (2FA).
![LIQUID GREEN](assets/fr/22.webp)

Và đó là, ví Liquid của bạn đã được tạo thành công bằng ứng dụng Green!

![LIQUID GREEN](assets/fr/23.webp)

Trước khi nhận bitcoins đầu tiên vào ví Liquid của bạn, **tôi khuyên bạn nên thực hiện một bài kiểm tra khôi phục rỗng**. Ghi lại thông tin tham chiếu, như xpub của bạn hoặc địa chỉ nhận đầu tiên, sau đó xóa ví của bạn trên ứng dụng Green khi nó vẫn còn trống. Tiếp theo, thử khôi phục ví của bạn trên Green bằng cách sử dụng bản sao lưu giấy của bạn. Kiểm tra xem thông tin chứng thực được tạo sau khi khôi phục có khớp với thông tin bạn ban đầu ghi chú hay không. Nếu có, bạn có thể yên tâm rằng bản sao lưu giấy của bạn là đáng tin cậy. Để tìm hiểu thêm về cách thực hiện một bài kiểm tra khôi phục, tôi khuyên bạn nên tham khảo hướng dẫn khác này:

https://planb.network/tutorials/wallet/recovery-test

## Thiết lập ví Liquid của bạn

Nếu bạn muốn tùy chỉnh ví của mình, nhấp vào ba chấm nhỏ ở góc trên bên phải.

![LIQUID GREEN](assets/fr/24.webp)

Tùy chọn "*Rename*" cho phép bạn tùy chỉnh tên của ví, điều này rất hữu ích nếu bạn quản lý nhiều ví trên cùng một ứng dụng.

![LIQUID GREEN](assets/fr/25.webp)

Menu "*Unit*" cho bạn lựa chọn thay đổi đơn vị cơ bản của ví. Ví dụ, bạn có thể chọn hiển thị nó bằng satoshis thay vì bitcoins.

![LIQUID GREEN](assets/fr/26.webp)

Menu "*Settings*" cung cấp quyền truy cập vào các tùy chọn khác nhau của ví Bitcoin của bạn.

![LIQUID GREEN](assets/fr/27.webp)

Ở đây bạn sẽ tìm thấy, ví dụ, *descriptor* của bạn có thể hữu ích nếu bạn dự định thiết lập một ví chỉ xem từ ví Liquid này.

![LIQUID GREEN](assets/fr/28.webp)

Bạn cũng có thể thay đổi mã PIN của ví và kích hoạt đăng nhập sinh trắc học.

![LIQUID GREEN](assets/fr/29.webp)

## Sử dụng ví Liquid của bạn

Bây giờ ví Liquid của bạn đã được thiết lập, bạn đã sẵn sàng để nhận L-sats đầu tiên của mình!
Nếu bạn chưa sở hữu L-BTC, có một số lựa chọn có sẵn cho bạn. Lựa chọn đầu tiên là có nó được gửi trực tiếp cho bạn. Nếu ai đó muốn trả bạn bằng bitcoins trên Liquid, chỉ cần đưa họ một địa chỉ nhận. Giải pháp khác là trao đổi bitcoins onchain của bạn hoặc những cái trên mạng Lightning cho L-BTC. Để làm điều này, bạn có thể sử dụng [một cầu như Boltz](https://boltz.exchange/). Chỉ cần nhập địa chỉ Liquid của bạn trên trang web, sau đó thực hiện thanh toán qua mạng Lightning hoặc onchain.
![LIQUID GREEN](assets/fr/30.webp)

Để tạo một địa chỉ Liquid, nhấp vào nút "*Receive*".

![LIQUID GREEN](assets/fr/31.webp)

Green sau đó sẽ hiển thị địa chỉ nhận trống đầu tiên của ví bạn. Bạn có thể quét mã QR kèm theo hoặc sao chép địa chỉ trực tiếp để gửi L-BTC vào đó.

![LIQUID GREEN](assets/fr/32.webp)

Khi giao dịch được phát sóng trên mạng, nó sẽ xuất hiện trong ví của bạn.

![LIQUID GREEN](assets/fr/33.webp)

Chờ đợi để nhận đủ xác nhận để coi giao dịch là cuối cùng. Trên Liquid, xác nhận nên nhanh chóng, vì một khối được công bố mỗi phút.

![LIQUID GREEN](assets/fr/34.webp)
Với L-sats trong ví Liquid của bạn, giờ đây bạn cũng có thể gửi chúng. Nhấp vào "*Gửi*".
![LIQUID GREEN](assets/fr/35.webp)

Trên trang tiếp theo, nhập địa chỉ Liquid của người nhận. Bạn có thể nhập thủ công hoặc quét mã QR của họ.

![LIQUID GREEN](assets/fr/36.webp)

Chọn số lượng của khoản thanh toán.

![LIQUID GREEN](assets/fr/37.webp)

Nhấp vào "*Tiếp theo*" để truy cập màn hình tóm tắt giao dịch của bạn. Kiểm tra xem địa chỉ, số lượng và phí có chính xác không.

![LIQUID GREEN](assets/fr/38.webp)

Nếu mọi thứ đều ổn với bạn, hãy trượt nút màu xanh ở cuối màn hình sang phải để ký và phát sóng giao dịch trên mạng Bitcoin.

![LIQUID GREEN](assets/fr/39.webp)

Giao dịch của bạn giờ đây sẽ xuất hiện trên bảng điều khiển của ví Bitcoin của bạn chờ xác nhận.

![LIQUID GREEN](assets/fr/40.webp)

Và đó là tất cả, bạn giờ đã biết cách sử dụng chuỗi phụ Liquid một cách dễ dàng với ứng dụng Blockstream Green!

Nếu bạn thấy hướng dẫn này hữu ích, tôi sẽ rất trân trọng nếu bạn để lại một lượt thích bên dưới. Đừng ngần ngại chia sẻ bài viết này trên các mạng xã hội của bạn. Cảm ơn bạn rất nhiều!

Tôi cũng khuyên bạn nên khám phá hướng dẫn hoàn chỉnh khác này về ứng dụng di động Blockstream Green để thiết lập một ví Bitcoin hot onchain:

https://planb.network/tutorials/wallet/blockstream-green