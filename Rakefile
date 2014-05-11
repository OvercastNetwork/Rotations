require 'net/http'
require 'openssl'
require 'json'

task :default => [:verify]

task :verify do
    datacenters = ['US', 'EU']
    files = []
    maps = []

    datacenters.each do |datacenter|
        files += Dir[datacenter + "/*"];
    end

    files.each do |file|
        File.open(file, "r") do |io|
            maps += io.read.split("\n")
        end
    end

    maps.uniq!

    uri = URI.parse("https://cdn.oc.tc")
    http = Net::HTTP.new(uri.host, uri.port)
    http.use_ssl = true
    http.verify_mode = OpenSSL::SSL::VERIFY_NONE
    request = Net::HTTP::Post.new("/rotations/verify.php")
    request.add_field('Content-Type', 'application/json')
    request.body = {:maps => maps}.to_json
    response = http.request(request)

    unless response.code.to_i == 200
        fail "Bad maps:\n\n" + JSON.pretty_generate(JSON.parse(response.body)) + "\n\n"
    end
end
