---
layout: page
title: Contact Us
permalink: /contact
footer_script: |
    <script>
        jQuery(document).ready(function($) {
            var directionDisplay;
            var directionsService = new google.maps.DirectionsService();
            var map;

            function initialize() {
                var latlng = new google.maps.LatLng(28.666239, 77.100885);
                // set direction render options
                var rendererOptions = {
                    draggable: true,
                    polylineOptions: {
                        strokeColor: '#f30c74'
                    }
                };
                directionsDisplay = new google.maps.DirectionsRenderer(rendererOptions);
                var myOptions = {
                    zoom: 15,
                    center: latlng,
                    mapTypeId: google.maps.MapTypeId.ROADMAP,
                    mapTypeControl: false,
                    scrollwheel: 1,
                    styles: [{
                        "featureType": "all",
                        "stylers": [{
                            "saturation": 0
                        }, {
                            "hue": "#e7ecf0"
                        }]
                    }, {
                        "featureType": "road",
                        "stylers": [{
                            "saturation": -70
                        }]
                    }, {
                        "featureType": "transit",
                        "stylers": [{
                            "visibility": "off"
                        }]
                    }, {
                        "featureType": "poi",
                        "stylers": [{
                            "visibility": "off"
                        }]
                    }, {
                        "featureType": "water",
                        "stylers": [{
                            "visibility": "simplified"
                        }, {
                            "saturation": -60
                        }]
                    }]
                };
                // add the map to the map placeholder
                map = new google.maps.Map(document.getElementById("map_canvas"), myOptions);
                directionsDisplay.setMap(map);
                directionsDisplay.setPanel(document.getElementById("directionsPanel"));
                // Add a marker to the map for the end-point of the directions.
                var marker = new google.maps.Marker({
                    position: latlng,
                    map: map,
                    title: "Hanoi University",
                    icon: 'images/map-icon.png'
                });
            }

            /*hdv*/
            function makeMarker(position, icon, title) {
                new google.maps.Marker({
                    position: position,
                    map: map,
                    icon: icon,
                    title: title
                });
            };
            var movingIcon = new google.maps.MarkerImage('');
            var startIcon = new google.maps.MarkerImage('');
            /*end hdv*/
            
            initialize();
            $('#routeForm').on('submit', function() {
                calcRoute();
                $('.apimap_form').css('overflow-y', 'scroll');
                $('#directionsPanel').css('border-color', '#dadada');
                return false;
            });

            $('.c-radio label span.check-checkbox').click(function(event) {
                $('.c-radio label span.check-checkbox').removeClass('active');
                $(this).addClass('active');
            });
        });
    </script>
---
<section class="fw-main-row">
    <div class="fw-main-row-bg"></div>
    <div class="fw-main-row-overlay has-color"></div>
    <div class="fw-container ">        
        <div class="fw-row">
            <div class="fw-col-xs-12 fw-col-sm-6 padding-bottom50px">
                <div class="ht-contact-form form-wrapper contact-form">
                    <form data-fw-form-id="fw_form" class="fw_form_fw_form" method="post" action="" data-fw-ext-forms-type="contact-forms">
                        <input type="hidden" name="fwf" value="fw_form" />
                        <input type="hidden" id="_nonce_271fca0b2bb618b7f84815c4d944dab4" name="_nonce_271fca0b2bb618b7f84815c4d944dab4" value="d294100792" />
                        <input type="hidden" name="_wp_http_referer" value="/" />
                        <input type="hidden" name="fw_ext_forms_form_type" value="contact-forms" />
                        <input type="hidden" name="fw_ext_forms_form_id" value="e38002fb3a7988a9b6ee37b8a5e97c46" />
                        <div class="wrap-forms">
                            <div class="fw-row"></div>
                            <div class="fw-row">
                                <div class="fw-col-xs-12 fw-col-sm-6 form-builder-item">
                                    <div class="field-text">
                                        <label for="id-3286">First Name <sup>*</sup> </label>
                                        <input type="text" name="text_e0de54e" id="id-3286">
                                    </div>
                                </div>
                                <div class="fw-col-xs-12 fw-col-sm-6 form-builder-item">
                                    <div class="field-text">
                                        <label for="id-3287">Last Name <sup>*</sup> </label>
                                        <input type="text" name="text_dc0769c" id="id-3287">
                                    </div>
                                </div>
                            </div>
                            <div class="fw-row">
                                <div class="fw-col-xs-12 fw-col-sm-6 form-builder-item">
                                    <div class="field-text">
                                        <label for="id-3288">Email <sup>*</sup> </label>
                                        <input type="text" name="email_5f64607" id="id-3288">
                                    </div>
                                </div>
                                <div class="fw-col-xs-12 fw-col-sm-6 form-builder-item">
                                    <div class="field-text">
                                        <label for="id-3289">Phone Number </label>
                                        <input type="text" name="text_8a668f9" id="id-3289">
                                    </div>
                                </div>
                            </div>
                            <div class="fw-row">
                                <div class="fw-col-xs-12 form-builder-item">
                                    <div class="field-textarea">
                                        <label for="id-3290">Message <sup>*</sup> </label>
                                        <textarea name="textarea_46e6c92" id="id-3290"></textarea>
                                        <p><em>*Note: Your email address will be kept secret and not be published</em></p>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="text-center">
                            <input type="submit" value="SUBMIT" />
                        </div>
                    </form>
                </div>
            </div>
            <div class="fw-col-xs-12 fw-col-sm-6">
                <div id="map_canvas" class="wow fadeInUp"></div>
                <div class="textblock-shortcode icon-box textblock-shortcode-007">
                    <h3 class="text-heading" style="color: #36392e;"><i class="ion-ios-location-outline inline"></i> <span>CONTACT INFO</span></h3>
                    <p>Flat No. 9, Janta Flats, Near Dashera Park,
                        <br>Jwala Heri Market, Paschim Vihar,
                        <br>Delhi-110063, India</p>
                    <p>Tel: 011 - 45548219</p>
                    <p>Mobile: +91 - 999 094 8511, 913 684 0830, 995 306 7873</p>
                    <p>Email: info@richlooksmakeupstudio.co.in</p>
                    <p>Time: 10:00 AM to 6:00 PM</p>
                </div>
            </div>
        </div>
        <div class="fw-row">
            <div class="fw-col-xs-12">
                <div class="fw-divider-space" style="padding-top: 30px;"></div>
            </div>
        </div>
    </div>
</section>
