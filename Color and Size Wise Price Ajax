
                      {{-- <div class="priceadd">
                                @foreach ($groupby as $price)
                                    <h3 class="price-detail getAttrPrice">${{ $price[0]->price }} .00<del>$459.00</del><span>55% off</span></h3>
                                @endforeach
                            </div> --}}
                            <div class="priceadd">
                                <h3 class="price-detail getAttrPrice">$45.00-$60.00<del>$459.00</del><span>55% off</span></h3>
                            </div>
                            <h6 class="product-title pb-2">Select Color</h6>
                            <ul class="color-variant coloradd" id="getColorToPrice">
                                @foreach ($groupby as $color)
                                <li class="color_id" value="{{ $color[0]->color_id }}" data-product="{{ $color[0]->product_id }}">{{ $color[0]->get_color->color_name }}</li>
                                @endforeach
                            </ul>
                            <div id="selectSize" class="addeffect-section product-description border-product">
                                <h6 class="product-title size-text">select size <span><a href="#" data-bs-toggle="modal"
                                            data-bs-target="#sizemodal">size
                                            chart</a></span></h6>
                                <div class="modal fade" id="sizemodal" tabindex="-1" role="dialog"
                                    aria-labelledby="exampleModalLabel" aria-hidden="true">
                                    <div class="modal-dialog modal-dialog-centered" role="document">
                                        <div class="modal-content">
                                            <div class="modal-header">
                                                <h5 class="modal-title" id="exampleModalLabel">Sheer
                                                    Straight Kurta</h5>
                                                <button type="button" class="btn-close" data-bs-dismiss="modal"
                                                    aria-label="Close"><span aria-hidden="true">&times;</span></button>
                                            </div>
                                            <div class="modal-body"><img src="../assets/images/size-chart.jpg" alt=""
                                                    class="img-fluid blur-up lazyload"></div>
                                        </div>
                                    </div>
                                </div>
                                <h6 class="error-message">please select size</h6>
                                <div class="size-box">
                                    <ul class="sizeadd" id="getSizeToPrice">
                                        @foreach ($groupby as $size)
                                            <li class="size_id" value="{{ $size[0]->size_id }}" data-product="{{ $size[0]->product_id }}">{{ $size[0]->get_size->size_name }}</li>
                                        @endforeach
                                    </ul>
                                </div>



// Route
// Route::get('/product/get/size/{color}/{product}', 'FrontEndController@GetSize')->name('GetSize');
// Route::get('/product/get/price/{size}/{product}', 'FrontEndController@GetPrice')->name('GetPrice');
// Route::post('/product/get/color/to/price', 'FrontEndController@GetColorToPrice')->name('GetColorToPrice');
Route::post('/product/get/size/to/price', 'FrontEndController@GetSizeToPrice')->name('GetSizeToPrice');
Route::post('/product/get/color/to/size', 'FrontEndController@GetColorToSize')->name('GetColorToSize');
Route::get('/product/get/color/{size}/{product}', 'FrontEndController@GetSizeWiseColor')->name('GetSizeWiseColor');
Route::get('/product/get/res/color/to/price/{color}/{product}', 'FrontEndController@GetResColorToPrice')->name('GetResColorToPrice');
Route::get('/product/get/color/wise/size/{color}/{product}', 'FrontEndController@GetColorWiseSize')->name('GetColorWiseSize');
Route::get('/product/get/size/wise/price/{size}/{product}', 'FrontEndController@GetSizeWisePrice')->name('GetSizeWisePrice');


// function GetSize($color, $product){
    //     $output = '';
    //     $sizes = Attributes::where('color_id', $color)->where('product_id', $product)->get();
    //     foreach ($sizes as $size) {
    //         // $output = $output . '<input type="radio" name="size" value="'.$size->size_id.'">'.$size->get_size->size_name.'';
    //         $output = $output . '<li class="sizeid" data-product="{{ $single_product->id }}" value="'.$size->size_id.'">'.$size->get_size->size_name.'</li>';
    //     }

    //     echo $output;
    // }


    // function GetPrice($size, $product){
    //     $output = '';
    //     $prices = Attributes::where('size_id', $size)->where('product_id', $product)->get();
    //     foreach ($prices as $price) {
    //         $output = $output . '<h3 class="price-detail" value="'.$price->price.'">'.$price->price.'.00<del>$459.00</del><span>55% off</span></h3>';
    //     }
    //     echo $output;
    // }


    // Size Wise Color Ajax Get Request
    function GetSizeWiseColor($size, $product){
        $output = '';
        $colors = Attributes::where('size_id', $size)->where('product_id', $product)->get();
        foreach ($colors as $color) {
            $output = $output . '<li class="color_id" data-product="'.$color->product_id.'" id="color_id" value="'.$color->color_id.'">'.$color->get_color->color_name.'</li>';
        }
        echo $output;
    }

    function GetColorWiseSize($color, $product){
        $output = '';
        $sizes = Attributes::where('color_id', $color)->where('product_id', $product)->get();
        foreach ($sizes as $sizename) {
            $output = $output . '<li class="size_id" data-product="'.$sizename->product_id.'" id="size_id" value="'.$sizename->size_id.'">'.$sizename->get_size->size_name.'</li>';
        }
        echo $output;
    }



// Color Wise Size Ajax Post Request
    // function GetColorToSize(Request $request){
    //     if ($request->ajax()) {
    //         $data = $request->all();
    //         // echo "<pre>"; print_r($data); die;
    //         $attrColorToSize = Attributes::where(['product_id' => $data['product_id']])->where(['color_id' => $data['color']])->first();
    //         return $attrColorToSize->get_size->size_name;
    //     }
    // }

// Size Wise Price Ajax Post Request
// function GetSizeToPrice(Request $request){
//     if ($request->ajax()) {
//         $data = $request->all();
//         // echo "<pre>"; print_r($data); die;
//         $attrSizeToPrice = Attributes::where(['product_id' => $data['product_id']])->where(['size_id' => $data['size']])->first();
//         return $attrSizeToPrice->price;
//     }
// }

// Size Wise Price Ajax Get Request
function GetSizeWisePrice($size, $product){
    $output = '';
    $prices = Attributes::where('size_id', $size)->where('product_id', $product)->get();
    $output = $output . '<h3 class="price-detail getAttrPrice">$'.$prices[0]->price.'.00<span>55% off</span></h3>';
    echo $output;
}


// Color Wise Price Ajax Get Request
    function GetResColorToPrice($color, $product){
        $output = '';
        $prices = Attributes::where('color_id', $color)->where('product_id', $product)->get();
        $output = $output . '<h3 class="price-detail getAttrPrice">$'.$prices[0]->price.'</h3>';
            echo $output;
    }

// Color Wise Price Ajax Post Request
    // function GetColorToPrice(Request $request){
    //     if ($request->ajax()) {
    //         $data = $request->all();
    //         // echo "<pre>"; print_r($data); die;
    //         $attrColorToPrice = Attributes::where(['product_id' => $data['product_id']])->where(['color_id' => $data['color']])->first();
    //         return $attrColorToPrice->price;
    //     }
    // }
    
    
    
    <script>
    $(document).ready(function(){
        // $(".color_id").click(function(){
        //     let colorid = $(this).val();
        //     let productid = $(this).attr('data-product');
        //     // alert(productid);
        //     $.ajax({
        //         type:"GET",
        //         url:"{{ url('product/get/size') }}/" + colorid + '/' + productid,
        //         success:function(res) {
        //             $('.sizeadd').html(res)
        //         }
        //     });
        // });





    // });
    // </script>
    // <script>
    //     $(".size_id").click(function(){
    //         let sizeid = $(this).val();
    //         let productid = $(this).attr('data-product');
    //         // alert(productid);
    //         $.ajax({
    //             type:"GET",
    //             url:"{{ url('product/get/price') }}/" + sizeid + '/' + productid,
    //             success:function(res) {
    //                 $('.priceadd').html(res)
    //                 // console.log(res)
    //             }
    //         });
    //     });
// Color to Price showing
        // $('.color_id').click(function(){
        //     let color = $(this).val();
        //     let product_id = $(this).attr('data-product');

        //     $.ajax({
        //         type:"post",
        //         url:'/product/get/color/to/price',
        //         data:{color:color,product_id:product_id},
        //         success:function(res) {
        //             $('.getAttrPrice').html("$" + res + ".00");
        //             // alert(res);
        //         }

        //     });
        // })

// Size to Price showing
        $('.size_id').click(function(){
            let size = $(this).val();
            let product_id = $(this).attr('data-product');

            $.ajax({
                type:"post",
                url:'/product/get/size/to/price',
                data:{size:size,product_id:product_id},
                success:function(res) {
                    $('.getAttrPrice').html("$" + res + ".00");
                    // alert(res);
                }

            });
        })

// Color to Size showing
        // $('.color_id').click(function(){
        //     let color = $(this).val();
        //     let product_id = $(this).attr('data-product');

        //     $.ajax({
        //         type:"post",
        //         url:'/product/get/color/to/size',
        //         data:{color:color,product_id:product_id},
        //         success:function(res) {
        //             $('.size_id').html(res);
        //             // alert(res);
        //         }

        //     });
        // })

        $(".size_id").click(function(){
            let sizeid = $(this).val();
            let productid = $(this).attr('data-product');
            // alert(productid);
            $.ajax({
                type:"GET",
                url:"{{ url('product/get/color') }}/" + sizeid + '/' + productid,
                success:function(res) {
                    $('.coloradd').html(res)
                    // console.log(res)
                    $(".color_id").click(function(){
                        let colorid = $(this).val();
                        let productid = $(this).attr('data-product');
                        // alert(productid);

                        $.ajax({
                            type:"get",
                            url: "{{ url('product/get/res/color/to/price') }}/" + colorid + '/' + productid,
                            success:function(res){
                                // alert(res);
                                $('.priceadd').html(res);
                            }
                        });
                    });

                }
            });
        });

        $('.color_id').click(function(){
            let colorid = $(this).val();
            let productid = $(this).attr('data-product');
            // alert(productid);
            $.ajax({
                type:"get",
                url: "{{ url('product/get/color/wise/size') }}/" + colorid + '/' + productid,
                success:function(res){
                // alert(res);
                $('.sizeadd').html(res);
                $(".size_id").click(function(){
                    let size_id = $(this).val();
                    let product_id = $(this).attr('data-product');
                    // alert(size_id);
                    $.ajax({
                        type:"get",
                        url:"{{ url('product/get/size/wise/price') }}/" + size_id + '/' + product_id,
                        success:function(res){
                            // alert(res);
                            $('.priceadd').html(res);
                        }
                    });
                });

                }
            });
        });
    </script>
