

apple_library(
    name='MyLib',
    module_name='MyLib',
    header_path_prefix='MyLib',
    visibility=['PUBLIC'],
    headers=glob([
        'Sources/**/*.h',
    ]),
    exported_headers=glob([
        'Sources/**/*.h',
    ], exclude=[
        'Sources/Nested/MyLibPrivateClass.h',
    ]),
    srcs=glob([
        'Sources/**/*.m',
    ]),
    tests=[
        ':MyLibTests',
    ],
    frameworks=[
        '$SDKROOT/System/Library/Frameworks/Foundation.framework'
    ]
)

apple_test(
    name='MyLibTests',
    module_name='MyLibTests',
    deps=[
        ':MyLib',
    ],
    info_plist='Tests/Info.plist',
    info_plist_substitutions={
        'PRODUCT_BUNDLE_IDENTIFIER': 'org.test.' + 'MyLibTests',
    },
    headers=glob([
        'Tests/**/*.h',
    ]),
    srcs=glob([
        'Tests/**/*.m',
    ]),
    frameworks=[
        '$PLATFORM_DIR/Developer/Library/Frameworks/XCTest.framework',
    ]
)